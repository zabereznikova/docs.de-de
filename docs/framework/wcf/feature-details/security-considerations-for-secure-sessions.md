---
title: Sicherheitsüberlegungen für Sicherheitssitzungen
ms.date: 03/30/2017
ms.assetid: 0d5be591-9a7b-4a6f-a906-95d3abafe8db
ms.openlocfilehash: 587897cc296523e0bfd5a4d4fa50b1e145cb69fb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601048"
---
# <a name="security-considerations-for-secure-sessions"></a>Sicherheitsüberlegungen für Sicherheitssitzungen
Berücksichtigen Sie die folgenden Punkte, die sich bei der Implementierung von Sicherheitssitzungen auf die Sicherheit auswirken. Weitere Informationen zu Sicherheitsüberlegungen finden Sie unter [Sicherheitsüberlegungen](security-considerations-in-wcf.md) und [bewährte Methoden für die Sicherheit](best-practices-for-security-in-wcf.md).  
  
## <a name="secure-sessions-and-metadata"></a>Sicherheitssitzungen und Metadaten  
 Wenn eine sichere Sitzung eingerichtet und die- <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> Eigenschaft auf festgelegt ist `false` , sendet Windows Communication Foundation (WCF) eine-Assertion `mssp:MustNotSendCancel` als Teil der Metadaten im Web Services Description Language (WSDL)-Dokument für den Dienst Endpunkt. Die `mssp:MustNotSendCancel`-Assertion informiert Clients, dass der Dienst nicht auf Anforderungen zum Abbrechen der sicheren Sitzung reagiert. Wenn die- <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.RequireCancellation%2A> Eigenschaft auf festgelegt ist `true` , gibt WCF keine-Assertionen `mssp:MustNotSendCancel` im WSDL-Dokument aus. Clients sollen eine Abbruchanforderung an den Dienst senden, wenn sie die sichere Sitzung nicht mehr benötigen. Wenn ein Client mit dem [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)generiert wird, reagiert der Client Code entsprechend auf das vorhanden sein oder Nichtvorhandensein der-Assertion `mssp:MustNotSendCancel` .  
  
## <a name="secure-conversations-and-custom-tokens"></a>Sichere Unterhaltungen und benutzerdefinierte Token  
 Beim Mischen benutzerdefinierter Token und abgeleiteter Schlüssel ergeben sich aufgrund der Art der Definition in der WS-SecureConversation-Spezifikation einige Probleme. Die Spezifikation besagt, dass `wsse:SecurityTokenReference` ein optionales Element ist, das auf das abgeleitete Token verweist: " `/wsc:DerivedKeyToken/wsse:SecurityTokenReference` dieses optionale Element wird verwendet, um das Sicherheitskontext Token, das Sicherheits Token oder den freigegebenen Schlüssel/geheimen Schlüssel anzugeben, der für die Ableitung verwendet wird. Wird das Element nicht angegeben, wird davon ausgegangen, dass der Empfänger den freigegebenen Schlüssel dem Nachrichtenkontext entnehmen kann. Wenn der Kontext nicht bestimmt werden kann, sollte ein Fehler wie z `wsc:UnknownDerivationSource` . b. ausgelöst werden. "  
  
 Das bedeutet, dass zum Ableiten eines benutzerdefinierten Tokens dessen Klauseltyp in ein `SecurityTokenReference`-Element eingeschlossen werden muss. Zwar steht eine Option zum Deaktivieren der Ableitung zur Verfügung, standardmäßig werden Schlüssel jedoch abgeleitet. Wird der Schlüssel nicht eingeschlossen, ist zwar die Serialisierung des abgeleiteten Schlüsseltokens erfolgreich, bei der Deserialisierung wird jedoch eine Ausnahme ausgelöst.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)
- [Sicherheitshinweise](security-considerations-in-wcf.md)
- [Bewährte Methoden für Sicherheit](best-practices-for-security-in-wcf.md)
