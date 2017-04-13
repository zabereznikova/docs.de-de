---
title: "Vorgehensweise: &#196;ndern des Kryptografieanbieters f&#252;r den privaten Schl&#252;ssel eines X.509-Zertifikats | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Kryptografieanbieter [WCF]"
  - "Kryptografieanbieter [WCF], Ändern"
ms.assetid: b4254406-272e-4774-bd61-27e39bbb6c12
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Vorgehensweise: &#196;ndern des Kryptografieanbieters f&#252;r den privaten Schl&#252;ssel eines X.509-Zertifikats
In diesem Thema wird erläutert, wie Sie den Kryptografieanbieter ändern, mit dessen Hilfe der private Schlüssel eines X.509\-Zertifikats bereitgestellt wird, und wie Sie den Anbieter in das [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Sicherheitsframework integrieren.  Weitere Informationen zum Verwenden von Zertifikaten finden Sie unter [Verwenden von Zertifikaten](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 Das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sicherheitsframework ermöglicht die Einführung neuer Sicherheitstokentypen, wie unter [Vorgehensweise: Erstellen eines benutzerdefinierten Tokens](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md) beschrieben.  Es ist auch möglich, ein benutzerdefiniertes Token zu verwenden, um vorhandene vom System bereitgestellte Tokentypen zu ersetzen.  
  
 In diesem Thema wird das vom System bereitgestellte X.509\-Sicherheitstoken durch ein benutzerdefiniertes X.509\-Token ersetzt, das für den privaten Schlüssel des Zertifikats eine andere Implementierung bereitstellt.  Dies ist bei Szenarios nützlich, bei denen der eigentliche private Schlüssel von einem anderen Kryptografieanbieter als dem standardmäßigen Kryptografieanbieter von Windows bereitgestellt wird.  Ein Beispiel für einen alternativen Kryptografieanbieter ist ein Hardwaresicherheitsmodul, das alle Kryptografievorgänge durchführt, die private Schlüssel betreffen, und das die privaten Schlüssel nicht im Arbeitsspeicher speichert. Auf diese Weise wird die Sicherheit des Systems erhöht.  
  
 Das folgende Beispiel dient nur der Veranschaulichung.  Es stellt keinen Ersatz für den standardmäßigen Kryptografieanbieter dar, aber es verdeutlicht, an welcher Stelle ein Anbieter dieser Art integriert werden kann.  
  
## Verfahren  
 Jedes Sicherheitstoken, das über einen zugeordneten Sicherheitsschlüssel bzw. mehrere Sicherheitsschlüssel verfügt, muss die <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A>\-Eigenschaft implementieren. Diese Eigenschaft gibt eine Auflistung der Schlüssel aus der Sicherheitstokeninstanz zurück.  Wenn es sich bei dem Token um ein X.509\-Sicherheitstoken handelt, enthält die Auflistung eine einzelne Instanz der <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>\-Klasse, die sowohl öffentliche als auch private Schlüssel darstellt, die dem Zertifikat zugeordnet sind.  Erstellen Sie eine neue Implementierung dieser Klasse, um den standardmäßigen Kryptografieanbieter zu ersetzen, der zum Bereitstellen der Zertifikatschlüssel verwendet wird.  
  
#### So erstellen Sie einen benutzerdefinierten asymmetrischen X.509\-Schlüssel  
  
1.  Definieren Sie eine neue von der <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>\-Klasse abgeleitete Klasse.  
  
2.  Überschreiben Sie die schreibgeschützte <xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A>\-Eigenschaft.  Diese Eigenschaft gibt die tatsächliche Schlüsselgröße für das Paar aus öffentlichem und privatem Schlüssel des Zertifikats zurück.  
  
3.  Überschreiben Sie die <xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A>\-Methode.  Diese Methode wird vom [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sicherheitsframework aufgerufen, um einen symmetrischen Schlüssel mit dem privaten Schlüssel des Zertifikats zu entschlüsseln.  \(Der Schlüssel wurde vorher mit dem öffentlichen Schlüssel des Zertifikats verschlüsselt.\)  
  
4.  Überschreiben Sie die <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A>\-Methode.  Diese Methode wird vom [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sicherheitsframework aufgerufen, um eine Instanz der <xref:System.Security.Cryptography.AsymmetricAlgorithm>\-Klasse zu erhalten, die den Kryptografieanbieter entweder für den privaten oder den öffentlichen Schlüssel des Zertifikats darstellt. Dies hängt von den Parametern ab, die an die Methode übergeben werden.  
  
5.  Dies ist optional.  Überschreiben Sie die <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A>\-Methode.  Überschreiben Sie diese Methode, wenn eine andere Implementierung der <xref:System.Security.Cryptography.HashAlgorithm>\-Klasse erforderlich ist.  
  
6.  Überschreiben Sie die <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A>\-Methode.  Diese Methode gibt eine Instanz der <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>\-Klasse zurück, die dem privaten Schlüssel des Zertifikats zugeordnet ist.  
  
7.  Überschreiben Sie die <xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A>\-Methode.  Diese Methode wird verwendet, um anzugeben, ob ein bestimmter Kryptografiealgorithmus von der Implementierung des Sicherheitsschlüssels unterstützt wird.  
  
     [!code-csharp[c_CustomX509Token#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#1)]
     [!code-vb[c_CustomX509Token#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#1)]  
  
 Die folgende Prozedur zeigt, wie Sie die Implementierung des benutzerdefinierten asymmetrischen X.509\-Sicherheitsschlüssels, die in der vorherigen Prozedur erstellt wurde, auf das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sicherheitsframework abstimmen, um das vom System bereitgestellte X.509\-Sicherheitstoken zu ersetzen.  
  
#### So ersetzen Sie das vom System bereitgestellte X.509\-Sicherheitstoken durch ein benutzerdefiniertes asymmetrisches X.509\-Sicherheitsschlüsseltoken  
  
1.  Erstellen Sie ein benutzerdefiniertes X.509\-Sicherheitstoken, das anstelle des vom System bereitgestellten Sicherheitsschlüssels den benutzerdefinierten asymmetrischen X.509\-Sicherheitsschlüssel zurückgibt.  Weitere Informationen zu benutzerdefinierten Sicherheitstoken finden Sie unter [Vorgehensweise: Erstellen eines benutzerdefinierten Tokens](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
     [!code-csharp[c_CustomX509Token#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#2)]
     [!code-vb[c_CustomX509Token#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#2)]  
  
2.  Erstellen Sie einen benutzerdefinierten Sicherheitstokenanbieter, der ein benutzerdefiniertes X.509\-Sicherheitstoken zurückgibt. Dies ist im Beispiel gezeigt.  Weitere Informationen zu benutzerdefinierten Sicherheitstokenanbietern finden Sie unter [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md).  
  
     [!code-csharp[c_CustomX509Token#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#3)]
     [!code-vb[c_CustomX509Token#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#3)]  
  
3.  Wenn Sie den benutzerdefinierten Sicherheitsschlüssel auf der initiierenden Seite verwenden müssen, erstellen Sie einen benutzerdefinierten Clientsicherheitstoken\-Manager und benutzerdefinierte Clientanmeldeinformationen\-Klassen, wie im folgenden Beispiel gezeigt.  Weitere Informationen zu benutzerdefinierten Clientanmeldeinformationen und Clientsicherheitstoken\-Managern finden Sie unter [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client\- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomX509Token#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#4)]
     [!code-vb[c_CustomX509Token#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#4)]  
  
     [!code-csharp[c_CustomX509Token#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#6)]
     [!code-vb[c_CustomX509Token#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#6)]  
  
4.  Wenn Sie den benutzerdefinierten Sicherheitsschlüssel auf der Empfängerseite verwenden müssen, erstellen Sie einen benutzerdefinierten Dienstsicherheitstoken\-Manager und benutzerdefinierte Dienstanmeldeinformationen, wie im folgenden Beispiel gezeigt.  Weitere Informationen zu benutzerdefinierten Dienstanmeldeinformationen und Dienstsicherheitstoken\-Managern finden Sie unter [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client\- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
     [!code-csharp[c_CustomX509Token#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#5)]
     [!code-vb[c_CustomX509Token#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#5)]  
  
     [!code-csharp[c_CustomX509Token#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#7)]
     [!code-vb[c_CustomX509Token#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#7)]  
  
## Siehe auch  
 <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>   
 <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey>   
 <xref:System.IdentityModel.Tokens.SecurityKey>   
 <xref:System.Security.Cryptography.AsymmetricAlgorithm>   
 <xref:System.Security.Cryptography.HashAlgorithm>   
 <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>   
 [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client\- und Dienstanmeldeinformationen](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)   
 [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenauthentifizierers](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)   
 [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)   
 [Vorgehensweise: Erstellen eines benutzerdefinierten Tokens](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)   
 [Security Architecture](http://msdn.microsoft.com/de-de/16593476-d36a-408d-808c-ae6fd483e28f)