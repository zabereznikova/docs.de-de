---
title: 'Vorgehensweise: Erstellen eines Sicherheitstokendiensts'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, federation
- federation
ms.assetid: 98e82101-4cff-4bb8-a220-f7abed3556e5
caps.latest.revision: 12
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 827fef90a6277387ceac1c8f1d6df00a69a5d612
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-security-token-service"></a>Vorgehensweise: Erstellen eines Sicherheitstokendiensts
Ein Sicherheitstokendienst implementiert das in der WS-Trust-Spezifikation definierte Protokoll. Dieses Protokoll definiert Meldungsformate und Meldungsaustauschmuster zum Herausgeben, Erneuern, Abbrechen und Überprüfen von Sicherheitstoken. Ein angegebener Sicherheitstokendienst stellt eine oder mehrere dieser Fähigkeiten zur Verfügung. Dieses Thema behandelt das am häufigsten verwendete Szenario: das Implementieren der Tokenausstellung.  
  
## <a name="issuing-tokens"></a>Ausstellen von Token  
 WS-Trust definiert Meldungsformate basierend auf dem `RequestSecurityToken`-XSD-Schemaelement (XML Schema Definition Language) und dem `RequestSecurityTokenResponse`-XSD-Schemaelement zum Durchführen der Tokenausstellung. Außerdem definiert WS-Trust die zugeordneten Aktions-URIs (Action Uniform Resource Identifiers). Der Aktions-URI mit der `RequestSecurityToken` Nachricht http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue. Der Aktions-URI mit der `RequestSecurityTokenResponse` Nachricht http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue.  
  
### <a name="request-message-structure"></a>Anforderungsmeldungsstruktur  
 Die Anforderungsmeldungsstruktur für Probleme besteht normalerweise aus den folgenden Elementen:  
  
-   Geben Sie eine Anforderung URI mit einem Wert von http://schemas.xmlsoap.org/ws/2005/02/trust/Issue.  
  
-   Ein Tokentyp-URI Für Security Assertions Markup Language (SAML) 1.1-Token ist der Wert dieses URIs http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1.  
  
-   Ein Schlüsselgrößenwert, der die Anzahl der Bits im Schlüssel angibt, der dem ausgestellten Token zugeordnet werden soll.  
  
-   Ein Schlüsseltyp-URI Für symmetrische Schlüssel ist der Wert dieses URIs http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey.  
  
 Außerdem könnten ein paar andere Elemente vorhanden sein:  
  
-   Schlüsselmaterial, das vom Client bereitgestellt wird  
  
-   Umfangsinformationen, die den Zieldienst angeben, mit dem das ausgestellte Token verwendet wird  
  
 Der Sicherheitstokendienst verwendet die Informationen in der Problemanforderungsmeldung für die Erstellung der Problemantwortmeldung.  
  
## <a name="response-message-structure"></a>Antwortmeldungsstruktur  
 Die Antwortmeldungsstruktur für Probleme besteht normalerweise aus den folgenden Elementen:  
  
-   dem ausgestellten Sicherheitstoken, z. B. eine SAML 1.1-Assertion  
  
-   einem dem Sicherheitstoken zugeordnete Prüftoken. Für symmetrische Schlüssel ist dies oft eine verschlüsselte Form des Schlüsselmaterials.  
  
-   Verweise auf das ausgestellte Sicherheitstoken Der Sicherheitstokendienst gibt normalerweise einen Verweis zurück, der verwendet werden kann, wenn das ausgestellte Token in einer vom Client gesendeten nachfolgenden Meldung angezeigt wird, und einen Verweis, der verwendet werden kann, wenn das Token in nachfolgenden Meldungen nicht vorhanden ist.  
  
 Außerdem könnten ein paar andere Elemente vorhanden sein:  
  
-   Vom Sicherheitstokendienst bereitgestelltes Schlüsselmaterial  
  
-   Der zum Berechnen des freigegebenen Schlüssels benötigte Algorithmus  
  
-   Lebensdauerinformationen für das ausgestellte Token.  
  
## <a name="processing-request-messages"></a>Verarbeiten von Anforderungsmeldungen  
 Der Sicherheitstokendienst verarbeitet die Problemanforderung durch Untersuchen der verschiedenen Teile der Anforderungsmeldung und durch Sicherstellen der Ausstellung eines Tokens, das der Anforderung entspricht. Der Sicherheitstokendienst muss Folgendes bestimmen, bevor er das auszustellende Token erstellt:  
  
-   Die Anforderung ist tatsächlich eine Anforderung für ein auszustellendes Token.  
  
-   Der Sicherheitstokendienst unterstützt den angeforderten Tokentyp.  
  
-   Der Anforderungsdienst wird zum Erstellen der Anforderungen autorisiert.  
  
-   Der Sicherheitstokendienst kann den Erwartungen des Anforderungsdiensts in Bezug auf das Schlüsselmaterial entsprechen.  
  
 Zwei wichtige Teile beim Erstellen eines Tokens bestehen im Bestimmen des Schlüssels, mit dem das Token signiert werden soll, und des Schlüssels, mit dem der freigegebene Schlüssel verschlüsselt werden soll. Das Token muss signiert werden, damit der Dienst ermitteln kann, ob das Token von einem Sicherheitstokendienst ausgestellt wurde, dem er vertraut, wenn der Client dem Zieldienst das Token bereitstellt. Das Schlüsselmaterial muss in einer Art und Weise verschlüsselt werden, dass der Zieldienst das Schlüsselmaterial entschlüsseln kann.  
  
 Das Signieren einer SAML-Assertion schließt das Erstellen einer <xref:System.IdentityModel.Tokens.SigningCredentials>-Instanz ein. Der Konstruktor für diese Klasse kann Folgendes sein:  
  
-   Ein <xref:System.IdentityModel.Tokens.SecurityKey> für den Schlüssel zum Signieren der SAML-Assertion  
  
-   Eine Zeichenfolge, die den zu verwendenden Signaturalgorithmus identifiziert  
  
-   Eine Zeichenfolge, die den zu verwendenden Hashwertalgorithmus identifiziert  
  
-   Optional ein <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>, der den Schlüssel identifiziert, der zum Signieren der Assertion verwendet werden soll.  
  
 [!code-csharp[c_CreateSTS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#1)]
 [!code-vb[c_CreateSTS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#1)]  
  
 Das Verschlüsseln des freigegebenen Schlüssels schließt das Verschlüsseln des Schlüsselmaterials mit einem Schlüssel ein, den der Zieldienst zum Entschlüsseln des freigegeben Schlüssels verwenden kann. Normalerweise wird der öffentliche Schlüssel des Zieldiensts verwendet.  
  
 [!code-csharp[c_CreateSTS#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#2)]
 [!code-vb[c_CreateSTS#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#2)]  
  
 Außerdem wird ein <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> für den verschlüsselten Schlüssel benötigt.  
  
 [!code-csharp[c_CreateSTS#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#3)]
 [!code-vb[c_CreateSTS#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#3)]  
  
 Dieser <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier> wird dann zum Erstellen eines `SamlSubject` als Teil des `SamlToken` verwendet.  
  
 [!code-csharp[c_CreateSTS#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#4)]
 [!code-vb[c_CreateSTS#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#4)]  
  
 Weitere Informationen finden Sie unter [Verbundbeispiel](../../../../docs/framework/wcf/samples/federation-sample.md).  
  
## <a name="creating-response-messages"></a>Erstellen von Antwortmeldungen  
 Sobald der Sicherheitstokendienst die Problemanforderung verarbeitet und das auszustellende Token zusammen mit dem Prüfschlüssel erstellt, muss die Antwortmeldung erstellt werden, die mindestens das angeforderte Token, das Prüftoken und die ausgestellten Tokenverweise enthalten muss. Das ausgestellte Token ist normalerweise ein aus der <xref:System.IdentityModel.Tokens.SamlSecurityToken> erstelltes <xref:System.IdentityModel.Tokens.SamlAssertion>, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[c_CreateSTS#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#5)]
 [!code-vb[c_CreateSTS#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#5)]  
  
 Wenn der Sicherheitstokendienst das freigegebene Schlüsselmaterial bereitstellt, wird das Prüftoken durch Erstellen eines <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken> erstellt.  
  
 [!code-csharp[c_CreateSTS#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#6)]
 [!code-vb[c_CreateSTS#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#6)]  
  
 Weitere Informationen, wie das Prüftoken erstellt, wenn sowohl der Client als auch dem Sicherheitstokendienst Schlüsselmaterial für den gemeinsam verwendeten Schlüssel bereitstellt, finden Sie unter [Verbundbeispiel](../../../../docs/framework/wcf/samples/federation-sample.md).  
  
 Die ausgestellten Tokenverweise werden durch Erstellen von Instanzen der <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>-Klasse erstellt.  
  
 [!code-csharp[c_CreateSTS#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#7)]
 [!code-vb[c_CreateSTS#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#7)]  
  
 Diese verschiedenen Werte werden dann in der Antwortmeldung, die an den Client zurückgegeben wird, serialisiert.  
  
## <a name="example"></a>Beispiel  
 Vollständige Code für einen Sicherheitstokendienst finden Sie unter [Verbundbeispiel](../../../../docs/framework/wcf/samples/federation-sample.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IdentityModel.Tokens.SigningCredentials>  
 <xref:System.IdentityModel.Tokens.SecurityKey>  
 <xref:System.IdentityModel.Tokens.SecurityKeyIdentifier>  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
 <xref:System.IdentityModel.Tokens.SamlAssertion>  
 <xref:System.ServiceModel.Security.Tokens.BinarySecretSecurityToken>  
 <xref:System.IdentityModel.Tokens.SecurityKeyIdentifierClause>  
 [Verbundbeispiel](../../../../docs/framework/wcf/samples/federation-sample.md)
