---
title: "Sicherheitsüberlegungen für Sicherheitssitzungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: be460249ed877b2f67f2d153c2aea4a3cc4d2b37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="security-considerations-for-secure-sessions"></a>Sicherheitsüberlegungen für Sicherheitssitzungen
Berücksichtigen Sie die folgenden Punkte, die sich bei der Implementierung von Sicherheitssitzungen auf die Sicherheit auswirken. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Überlegungen zur Sicherheit, finden Sie unter [Sicherheitsüberlegungen](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md) und [Best Practices für Sicherheit](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
## <a name="secure-sessions-and-metadata"></a>Sicherheitssitzungen und Metadaten  
 Wenn eine sichere Sitzung eingerichtet und die <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A>-Eigenschaft auf `false` festgelegt ist, sendet [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] eine `mssp:MustNotSendCancel`-Assertion als Bestandteil der Metadaten im WSDL-Dokument (Web Services Description Language) für den Dienstendpunkt. Die `mssp:MustNotSendCancel`-Assertion informiert Clients, dass der Dienst nicht auf Anforderungen zum Abbrechen der sicheren Sitzung reagiert. Wenn die <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A>-Eigenschaft auf `true` gesetzt ist, gibt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] keine `mssp:MustNotSendCancel`-Assertion im WSDL-Dokument aus. Clients sollen eine Abbruchanforderung an den Dienst senden, wenn sie die sichere Sitzung nicht mehr benötigen. Wenn ein Client mit generiert wird die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), der Clientcode reagiert entsprechend, um das Vorhandensein oder fehlen der `mssp:MustNotSendCancel` Assertion.  
  
## <a name="secure-conversations-and-custom-tokens"></a>Sichere Unterhaltungen und benutzerdefinierte Token  
 Beim Mischen benutzerdefinierter Token und abgeleiteter Schlüssel ergeben sich aufgrund der Art der Definition in der WS-SecureConversation-Spezifikation einige Probleme. Laut Spezifikation `wsse:SecurityTokenReference` ist ein optionales Element, die das abgeleitete Token verweist: "`/wsc:DerivedKeyToken/wsse:SecurityTokenReference` dieses optionale Element wird verwendet, um Sicherheitskontexttoken, Sicherheitstoken oder freigegebenen Schlüssel/geheime Schlüssel für die Ableitung anzugeben. Wird das Element nicht angegeben, wird davon ausgegangen, dass der Empfänger den freigegebenen Schlüssel dem Nachrichtenkontext entnehmen kann. Wenn der Kontext nicht bestimmt werden kann, klicken Sie dann einen Fehler wie z. B. `wsc:UnknownDerivationSource` ausgelöst werden soll. "  
  
 Das bedeutet, dass zum Ableiten eines benutzerdefinierten Tokens dessen Klauseltyp in ein `SecurityTokenReference`-Element eingeschlossen werden muss. Zwar steht eine Option zum Deaktivieren der Ableitung zur Verfügung, standardmäßig werden Schlüssel jedoch abgeleitet. Wird der Schlüssel nicht eingeschlossen, ist zwar die Serialisierung des abgeleiteten Schlüsseltokens erfolgreich, bei der Deserialisierung wird jedoch eine Ausnahme ausgelöst.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 [Sicherheitsüberlegungen](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [Bewährte Methoden für Sicherheit](../../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)
