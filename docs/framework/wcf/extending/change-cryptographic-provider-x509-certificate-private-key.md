---
title: 'Vorgehensweise: Ändern des Kryptografieanbieters für den privaten Schlüssel eines X.509-Zertifikats'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptographic provider [WCF], changing
- cryptographic provider [WCF]
ms.assetid: b4254406-272e-4774-bd61-27e39bbb6c12
ms.openlocfilehash: 33d42f26407787b26e1447f8b8f619dd6fc15229
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262111"
---
# <a name="how-to-change-the-cryptographic-provider-for-an-x509-certificates-private-key"></a>Vorgehensweise: Ändern des Kryptografieanbieters für den privaten Schlüssel eines X.509-Zertifikats

In diesem Thema wird gezeigt, wie Sie den Kryptografieanbieter ändern, mit dem der private Schlüssel eines X. 509-Zertifikats bereitgestellt wird, und wie Sie den Anbieter in das Windows Communication Foundation (WCF)-Sicherheits Framework integrieren. Weitere Informationen zur Verwendung von Zertifikaten finden Sie unter [Arbeiten mit Zertifikaten](../feature-details/working-with-certificates.md).  
  
 Das WCF-Sicherheits Framework bietet eine Möglichkeit, neue Sicherheitstokentypen einzuführen, wie unter Gewusst [wie: Erstellen eines benutzerdefinierten](how-to-create-a-custom-token.md)Tokens beschrieben. Es ist auch möglich, ein benutzerdefiniertes Token zu verwenden, um vorhandene vom System bereitgestellte Tokentypen zu ersetzen.  
  
 In diesem Thema wird das vom System bereitgestellte X.509-Sicherheitstoken durch ein benutzerdefiniertes X.509-Token ersetzt, das für den privaten Schlüssel des Zertifikats eine andere Implementierung bereitstellt. Dies ist bei Szenarios nützlich, bei denen der eigentliche private Schlüssel von einem anderen Kryptografieanbieter als dem standardmäßigen Kryptografieanbieter von Windows bereitgestellt wird. Ein Beispiel für einen alternativen Kryptografieanbieter ist ein Hardwaresicherheitsmodul, das alle Kryptografievorgänge durchführt, die private Schlüssel betreffen, und das die privaten Schlüssel nicht im Arbeitsspeicher speichert. Auf diese Weise wird die Sicherheit des Systems erhöht.  
  
 Das folgende Beispiel dient nur der Veranschaulichung. Es stellt keinen Ersatz für den standardmäßigen Kryptografieanbieter dar, aber es verdeutlicht, an welcher Stelle ein Anbieter dieser Art integriert werden kann.  
  
## <a name="procedures"></a>Prozeduren  

 Jedes Sicherheitstoken, das über einen zugeordneten Sicherheitsschlüssel bzw. mehrere Sicherheitsschlüssel verfügt, muss die <xref:System.IdentityModel.Tokens.SecurityToken.SecurityKeys%2A>-Eigenschaft implementieren. Diese Eigenschaft gibt eine Auflistung der Schlüssel aus der Sicherheitstokeninstanz zurück. Wenn es sich bei dem Token um ein X.509-Sicherheitstoken handelt, enthält die Auflistung eine einzelne Instanz der <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>-Klasse, die sowohl öffentliche als auch private Schlüssel darstellt, die dem Zertifikat zugeordnet sind. Erstellen Sie eine neue Implementierung dieser Klasse, um den standardmäßigen Kryptografieanbieter zu ersetzen, der zum Bereitstellen der Zertifikatschlüssel verwendet wird.  
  
#### <a name="to-create-a-custom-x509-asymmetric-key"></a>So erstellen Sie einen benutzerdefinierten asymmetrischen X.509-Schlüssel  
  
1. Definieren Sie eine neue von der <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>-Klasse abgeleitete Klasse.  
  
2. Überschreiben Sie die schreibgeschützte <xref:System.IdentityModel.Tokens.SecurityKey.KeySize%2A>-Eigenschaft. Diese Eigenschaft gibt die tatsächliche Schlüsselgröße für das Paar aus öffentlichem und privatem Schlüssel des Zertifikats zurück.  
  
3. Überschreiben Sie die <xref:System.IdentityModel.Tokens.SecurityKey.DecryptKey%2A> -Methode. Diese Methode wird vom WCF-Sicherheits Framework aufgerufen, um einen symmetrischen Schlüssel mit dem privaten Schlüssel des Zertifikats zu entschlüsseln. (Der Schlüssel wurde vorher mit dem öffentlichen Schlüssel des Zertifikats verschlüsselt.)  
  
4. Überschreiben Sie die <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetAsymmetricAlgorithm%2A> -Methode. Diese Methode wird vom WCF-Sicherheits Framework aufgerufen, um eine Instanz der-Klasse zu erhalten, die <xref:System.Security.Cryptography.AsymmetricAlgorithm> den Kryptografieanbieter für den privaten oder öffentlichen Schlüssel des Zertifikats darstellt, abhängig von den Parametern, die an die-Methode weitergegeben werden.  
  
5. (Optional) Überschreiben Sie die <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetHashAlgorithmForSignature%2A> -Methode. Überschreiben Sie diese Methode, wenn eine andere Implementierung der <xref:System.Security.Cryptography.HashAlgorithm>-Klasse erforderlich ist.  
  
6. Überschreiben Sie die <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey.GetSignatureFormatter%2A> -Methode. Diese Methode gibt eine Instanz der <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>-Klasse zurück, die dem privaten Schlüssel des Zertifikats zugeordnet ist.  
  
7. Überschreiben Sie die <xref:System.IdentityModel.Tokens.SecurityKey.IsSupportedAlgorithm%2A> -Methode. Diese Methode wird verwendet, um anzugeben, ob ein bestimmter Kryptografiealgorithmus von der Implementierung des Sicherheitsschlüssels unterstützt wird.  
  
     [!code-csharp[c_CustomX509Token#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#1)]
     [!code-vb[c_CustomX509Token#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#1)]  
  
 Im folgenden Verfahren wird gezeigt, wie Sie die in der vorherigen Prozedur erstellte benutzerdefinierte Implementierung des asymmetrischen x. 509-Sicherheits Schlüssels mit dem WCF-Sicherheits Framework integrieren, um das vom System bereitgestellte x. 509-Sicherheits Token zu ersetzen.  
  
#### <a name="to-replace-the-system-provided-x509-security-token-with-a-custom-x509-asymmetric-security-key-token"></a>So ersetzen Sie das vom System bereitgestellte X.509-Sicherheitstoken durch ein benutzerdefiniertes asymmetrisches X.509-Sicherheitsschlüsseltoken  
  
1. Erstellen Sie ein benutzerdefiniertes X.509-Sicherheitstoken, das anstelle des vom System bereitgestellten Sicherheitsschlüssels den benutzerdefinierten asymmetrischen X.509-Sicherheitsschlüssel zurückgibt. Weitere Informationen zu benutzerdefinierten Sicherheits Token finden Sie unter Gewusst [wie: Erstellen eines benutzerdefinierten](how-to-create-a-custom-token.md)Tokens.  
  
     [!code-csharp[c_CustomX509Token#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#2)]
     [!code-vb[c_CustomX509Token#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#2)]  
  
2. Erstellen Sie einen benutzerdefinierten Sicherheitstokenanbieter, der ein benutzerdefiniertes X.509-Sicherheitstoken zurückgibt. Dies ist im Beispiel gezeigt. Weitere Informationen zu benutzerdefinierten Sicherheitstokenanbietern finden Sie unter Gewusst [wie: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters](how-to-create-a-custom-security-token-provider.md).  
  
     [!code-csharp[c_CustomX509Token#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#3)]
     [!code-vb[c_CustomX509Token#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#3)]  
  
3. Wenn Sie den benutzerdefinierten Sicherheitsschlüssel auf der initiierenden Seite verwenden müssen, erstellen Sie einen benutzerdefinierten Clientsicherheitstoken-Manager und benutzerdefinierte Clientanmeldeinformationen-Klassen, wie im folgenden Beispiel gezeigt. Weitere Informationen zu benutzerdefinierten Client Anmelde Informationen und Client Sicherheits Token-Managern finden Sie unter Exemplarische Vorgehensweise [: Erstellen von benutzerdefinierten Client-und Dienst Anmelde](walkthrough-creating-custom-client-and-service-credentials.md)Informationen.  
  
     [!code-csharp[c_CustomX509Token#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#4)]
     [!code-vb[c_CustomX509Token#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#4)]  
  
     [!code-csharp[c_CustomX509Token#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#6)]
     [!code-vb[c_CustomX509Token#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#6)]  
  
4. Wenn Sie den benutzerdefinierten Sicherheitsschlüssel auf der Empfängerseite verwenden müssen, erstellen Sie einen benutzerdefinierten Dienstsicherheitstoken-Manager und benutzerdefinierte Dienstanmeldeinformationen, wie im folgenden Beispiel gezeigt. Weitere Informationen über benutzerdefinierte Dienst Anmelde Informationen und Dienst Sicherheits Token-Manager finden Sie unter Exemplarische Vorgehensweise [: Erstellen von benutzerdefinierten Client-und Dienst Anmelde](walkthrough-creating-custom-client-and-service-credentials.md)Informationen.  
  
     [!code-csharp[c_CustomX509Token#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#5)]
     [!code-vb[c_CustomX509Token#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#5)]  
  
     [!code-csharp[c_CustomX509Token#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customx509token/cs/source.cs#7)]
     [!code-vb[c_CustomX509Token#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customx509token/vb/source.vb#7)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Tokens.X509AsymmetricSecurityKey>
- <xref:System.IdentityModel.Tokens.AsymmetricSecurityKey>
- <xref:System.IdentityModel.Tokens.SecurityKey>
- <xref:System.Security.Cryptography.AsymmetricAlgorithm>
- <xref:System.Security.Cryptography.HashAlgorithm>
- <xref:System.Security.Cryptography.AsymmetricSignatureFormatter>
- [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen](walkthrough-creating-custom-client-and-service-credentials.md)
- [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenauthentifizierers](how-to-create-a-custom-security-token-authenticator.md)
- [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters](how-to-create-a-custom-security-token-provider.md)
- [Vorgehensweise: Erstellen eines benutzerdefinierten Tokens](how-to-create-a-custom-token.md)
