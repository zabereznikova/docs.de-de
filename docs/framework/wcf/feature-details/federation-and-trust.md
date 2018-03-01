---
title: "Verbund und Vertrauenswürdigkeit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- federation [WCF], and trust
ms.assetid: 4bdec4f2-f8a2-4512-bdcf-14ef54b5877a
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 98b1274866dec2a4ca923d390f33df68449cf286
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="federation-and-trust"></a>Verbund und Vertrauenswürdigkeit
Dieses Thema deckt verschiedene Aspekte ab, die in Verbindung mit Verbundanwendungen, Vertrauensgrenzen und Konfiguration sowie dem Einsatz von ausgestellten Token in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] stehen.  
  
## <a name="services-security-token-services-and-trust"></a>Dienste, Sicherheitstokendienste und Vertrauenswürdigkeit  
 Dienste, die Verbundendpunkte verfügbar machen, erwarten normalerweise von den Clients, dass sie sich über ein Token authentifizieren, das von einem bestimmten Aussteller bereitgestellt wird. Der Dienst muss mit den richtigen Anmeldeinformationen für den Aussteller konfiguriert werden. Andernfalls kann er keine Signaturen über die ausgestellten Token überprüfen, und der Client kann nicht mit dem Dienst kommunizieren. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Aussteller-Anmeldeinformationen für den Dienst konfigurieren, finden Sie unter [Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).  
  
 Ähnlich verhält es sich mit Nutzung von symmetrischen Schlüsseln. Die Schlüssel werden für den Zieldienst verschlüsselt, d. h. der Sicherheitstokendienst muss mit den korrekten Anmeldeinformationen für den Zieldienst konfiguriert werden. Sonst kann er den Schlüssel für den Zieldienst nicht verschlüsseln und der Client kann auch hier nicht mit dem Dienst kommunizieren.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]Dienste verwenden Sie den Wert, der die <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> Eigenschaft auf die [SecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/securitybindingelement.md) Uhr uhrabweichung zwischen Client und Dienst ermöglichen. In einem Verbund gilt die Einstellung `MaxClockSkew` für Taktverschiebungen zwischen dem Client und dem Sicherheitstokendienst, von dem der Client das ausgestellte Token erhalten hat. Daher müssen die Sicherheitstokendienste keine Toleranz für Taktverschiebungen einberechnen, wenn die tatsächlichen Zeiten und die Ablaufzeiten des ausgestellten Tokens festgelegt werden.  
  
> [!NOTE]
>  Die Bedeutung der Taktverschiebung wächst mit abnehmender Lebensdauer des ausgestellten Tokens. In den meisten Fällen ist die Taktverschiebung kein großes Problem, wenn die Tokenlebensdauer 30 Minuten oder mehr beträgt. Szenarien mit kürzeren Lebensdauern oder Szenarien, bei denen die genaue Prüfzeit des Tokens wichtig ist, sollten so ausgelegt werden, dass sie die Taktverschiebung berücksichtigen.  
  
## <a name="federated-endpoints-and-time-outs"></a>Verbundendpunkte und Timeouts  
 Wenn ein Client mit einem Verbundendpunkt kommuniziert, muss er zunächst ein angemessenes Token von einem Sicherheitstokendienst erhalten. Wenn der Sicherheitstokendienst einen Verbundendpunkt verfügbar macht, muss der Client zunächst ein Token von dem Aussteller dieses Endpunkts anfordern. Jeder Tokenerwerb dauert eine gewisse Zeit, und während dieser Zeit fällt er unter das Gesamttimeout für das Senden der tatsächlichen Nachricht an den finalen Endpunkt.  
  
 Auf dem clientseitigen Kanal wird das Timeout z. B. auf 30 Sekunden festgelegt. Zwei Tokenaussteller müssen aufgefordert werden, Tokens abzurufen, bevor die Nachricht an den finalen Endpunkt verschickt wird; jeder benötigt für das Ausstellen eines Tokens 15 Sekunden. In diesem Fall schlägt der Versuch fehl, und eine <xref:System.TimeoutException> wird ausgelöst. Daher müssen Sie den Wert für <xref:System.ServiceModel.IContextChannel.OperationTimeout%2A> auf dem Clientkanal hoch genug festlegen, damit er auch die Zeit berücksichtigt, die das Abrufen aller ausgestellten Token in Anspruch nimmt. Sollte kein Wert für die Eigenschaft <xref:System.ServiceModel.IContextChannel.OperationTimeout%2A> festgelegt sein, muss die Eigenschaft <xref:System.ServiceModel.Channels.Binding.OpenTimeout%2A> oder die Eigenschaft <xref:System.ServiceModel.Channels.Binding.SendTimeout%2A> (oder beide) auf einen Wert festgelegt werden, der hoch genug ist, um die Zeit, die das Abrufen aller ausgestellten Token beansprucht, zu berücksichtigen.  
  
## <a name="token-lifetime-and-renewal"></a>Tokenlebensdauer und Erneuerung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients überprüfen das ausgestellte Token nicht, wenn sie eine ursprüngliche Anforderung an einen Dienst stellen.  Stattdessen vertraut [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] darauf, dass der Sicherheitstokendienst ein Token mit entsprechend wirksamen Zeiten und Ablaufzeiten ausgibt. Wenn das Token vom Client zwischengespeichert und wiederverwendet wird, wird die Tokenlebensdauer bei den folgenden Anforderungen überprüft, und der Client erneuert das Token ggf. automatisch. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Token zwischenspeichern, finden Sie unter [Vorgehensweise: Erstellen eines Clients Federated](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md).  
  
 Die Angabe von kurzen Lebensdauern (d. h. 30 Sekunden oder weniger für ausgestellte Token oder Sicherheitskontexttoken) kann zu Verhandlungstimeouts oder anderen Ausnahmen vonseiten der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients führen, wenn ausgestellte Token angefordert werden oder wenn Sicherheitskontexttoken verhandelt oder erneuert werden.  
  
## <a name="issued-tokens-and-inclusionmode"></a>Ausgestellte Token und InclusionMode  
 Ob ein ausgestelltes Token in einer Nachricht, die von einem Client an einen Verbundendpunkt gesendet wird, serialisiert wird, hängt von der Einstellung der Eigenschaft <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters.InclusionMode%2A> der Klasse <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters> ab. Diese Eigenschaft kann auf einen der <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>-Enumerationwerte festgelegt werden, ist aber in den meisten Verbundszenarien nutzlos. Die Werte `SecurityTokenInclusionMode.Never` und `SecurityTokenInclusionMode.AlwaysToInitiator` sorgen dafür, dass der Client einen Bezug an das Token sendet, das der Sicherheitstokendienst der vertrauenden Seite ausgestellt hat. Wenn die vertrauende Seite keine Kopie des ausgestellten Tokens besitzt, schlägt die Authentifizierung fehl, da der Tokenverweis nicht aufgelöst werden kann. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behandelt `SecurityTokenInclusionMode.Once` als gleichwertig zu `SecurityTokenInclusionMode.AlwaysToRecipient`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode>  
 [Vorgehensweise: Erstellen eines Verbundclients](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [Vorgehensweise: Erstellen einer WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
