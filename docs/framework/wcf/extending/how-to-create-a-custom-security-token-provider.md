---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
ms.openlocfilehash: 94de506b16d97ec82b84ec6eed34111e99f62977
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249266"
---
# <a name="how-to-create-a-custom-security-token-provider"></a>Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters

In diesem Thema wird beschrieben, wie Sie neue Tokentypen mit einem benutzerdefinierten Sicherheitstokenanbieter erstellen und den Anbieter in einen benutzerdefinierten Sicherheitstoken-Manager integrieren.  
  
> [!NOTE]
> Erstellen Sie einen benutzerdefinierten Tokenanbieter, wenn die im <xref:System.IdentityModel.Tokens>-Namespace gefundenen vom System bereitgestellten Token Ihren Anforderungen nicht entsprechen.  
  
 Der Sicherheitstokenanbieter erstellt eine Sicherheitstokendarstellung basierend auf Daten in den Client- oder Dienstanmeldeinformationen. Um den benutzerdefinierten Sicherheitstokenanbieter in Windows Communication Foundation (WCF)-Sicherheit zu verwenden, müssen Sie benutzerdefinierte Anmelde Informationen und Sicherheits Token-Manager-Implementierungen erstellen.  
  
 Weitere Informationen über benutzerdefinierte Anmelde Informationen und Sicherheits Token-Manager finden Sie unter Exemplarische Vorgehensweise [: Erstellen von benutzerdefinierten Client-und Dienst Anmelde](walkthrough-creating-custom-client-and-service-credentials.md)Informationen  
  
### <a name="to-create-a-custom-security-token-provider"></a>So erstellen Sie einen benutzerdefinierten Sicherheitstokenanbieter  
  
1. Definieren Sie eine neue von der <xref:System.IdentityModel.Selectors.SecurityTokenProvider>-Klasse abgeleitete Klasse.  
  
2. Implementieren Sie die <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>-Methode. Die Methode ist für die Erstellung und die Rückgabe einer Instanz des Sicherheitstokens verantwortlich. Im folgenden Beispiel wird eine Klasse mit der Bezeichnung `MySecurityTokenProvider` erstellt und die <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>-Methode überschrieben, um eine Instanz der <xref:System.IdentityModel.Tokens.X509SecurityToken>-Klasse zurückzugeben. Der Klassenkonstruktor erfordert eine neue Instanz der <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>-Klasse.  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a>So integrieren Sie einen benutzerdefinierten Sicherheitstokenanbieter in einen benutzerdefinierten Sicherheitstoken-Manager  
  
1. Definieren Sie eine neue von der <xref:System.IdentityModel.Selectors.SecurityTokenManager>-Klasse abgeleitete Klasse. (Das nachfolgende Beispiel ist von der <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>-Klasse abgeleitet, die von der <xref:System.IdentityModel.Selectors.SecurityTokenManager>-Klasse abgeleitet ist.)  
  
2. Überschreiben Sie die <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>-Methode, wenn sie noch nicht überschrieben ist.  
  
     Die- <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> Methode ist dafür verantwortlich, eine Instanz der-Klasse zurückzugeben, die dem-Parameter entspricht, der <xref:System.IdentityModel.Selectors.SecurityTokenProvider> <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> vom WCF-Sicherheits Framework an die-Methode übergeben wird. Ändern Sie die Methode zur Rückgabe der Implementierung des benutzerdefinierten Sicherheitstokenanbieters (die mit dem vorherigen Verfahren erstellt wurde), wenn die Methode mit einem entsprechenden Sicherheitstokenparameter aufgerufen wird. Weitere Informationen zum Sicherheits Token-Manager finden Sie unter Exemplarische Vorgehensweise [: Erstellen von benutzerdefinierten Client-und Dienst Anmelde](walkthrough-creating-custom-client-and-service-credentials.md)Informationen.  
  
3. Fügen Sie benutzerdefinierte Logik zur Methode hinzu, um diese zu befähigen, den benutzerdefinierten Sicherheitstokenanbieter basierend auf dem <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>-Parameter zurückzugeben. Im folgenden Beispiel wird der benutzerdefinierte Sicherheitstokenanbieter zurückgegeben, wenn die Tokenanforderungen erfüllt werden. Die Anforderungen umfassen ein  X.509-Sicherheitstoken und die Nachrichtenrichtung (die das Token für die Nachrichtenausgabe verwendet). In allen anderen Fällen ruft der Code die Basisklasse ab, um das vom System bereitgestellte Verhalten für andere Sicherheitstokenanforderungen zu verwalten.  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a>Beispiel  

 Im Folgenden wird eine vollständige <xref:System.IdentityModel.Selectors.SecurityTokenProvider>-Implementierung zusammen mit einer entsprechenden <xref:System.IdentityModel.Selectors.SecurityTokenManager>-Implementierung gezeigt.  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IdentityModel.Selectors.SecurityTokenProvider>
- <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.IdentityModel.Tokens.X509SecurityToken>
- [Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen](walkthrough-creating-custom-client-and-service-credentials.md)
- [Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenauthentifizierers](how-to-create-a-custom-security-token-authenticator.md)
