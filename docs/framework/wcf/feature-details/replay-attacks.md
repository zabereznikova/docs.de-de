---
title: Wiederholungsangriffe
ms.date: 03/30/2017
ms.assetid: 7a17e040-93cd-4432-81b9-9f62fec78c8f
ms.openlocfilehash: fefcb533cedb5405736ecda70c6879ebe00b8b49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186757"
---
# <a name="replay-attacks"></a>Wiederholungsangriffe
Ein *Wiederholungsangriff* tritt auf, wenn ein Angreifer einen Nachrichtenstream zwischen zwei Parteien kopiert und den Strom für eine oder mehrere Parteien wiedergibt. Wenn der Angriff nicht abgeschwächt wird, verarbeiten die angegriffenen Computer den Stream wie zulässige Nachrichten, was eine Reihe negativer Konsequenzen wie redundante Bestellungen eines Artikels zur Folge hat.  
  
## <a name="bindings-may-be-subject-to-reflection-attacks"></a>Bindungen sind möglicherweise Reflektionsangriffen ausgesetzt  
 *Reflektionsangriffe* Replays von Nachrichten an einen Sender sind, als ob sie vom Empfänger der Antwort stammt. Der Standard *replay-Erkennung* in der Windows Communication Foundation (WCF) Mechanismus wird nicht automatisch behandelt.  
  
 Reflektionsangriffe werden standardmäßig abgeschwächt, da die WCF-Dienstmodells eine signierte Nachrichtenkennung, für Anforderungsnachrichten hinzufügt und eine signierte erwartet `relates-to` Header in Antwortnachrichten. Infolgedessen kann die Anforderungsnachricht nicht als Antwort wiederholt werden. In sicheren Szenarien mit zuverlässigem Messaging werden Reflektionsangriffe aus folgenden Gründen abgemildert:  
  
-   Die Sequenzerstellung und die Sequenzerstellungsantwort verwenden unterschiedliche Nachrichtenschemas.  
  
-   Bei Simplexsequenzen können die vom Client gesendeten Nachrichten nicht wiedergegeben werden, da diese vom Client nicht interpretiert werden können.  
  
-   Bei Duplexsequenzen müssen die beiden Sequenzkennungen eindeutig sein. Ausgehende Nachrichten können daher nicht als eingehende Nachrichten wiederholt werden (alle Header und Texte werden ebenfalls signiert).  
  
 Aus diesem Grund sind nur Bindungen ohne WS-Adressierung anfällig für Reflektionsangriffe: benutzerdefinierte Bindungen, deren WS-Adressierung deaktiviert ist und die mit symmetrischen Schlüsseln gesichert sind. Die <xref:System.ServiceModel.BasicHttpBinding> verwendet standardmäßig keine WS-Adressierung; die Absicherung durch symmetrische Schlüssel erfolgt jedoch auf eine Art und Weise, die sie anfällig gegenüber dieser Art von Angriffen macht.  
  
 Zur Entschärfung für benutzerdefinierte Bindungen sollte auf einen Sicherheitskontext verzichtet werden, oder es sollten Header für die WS-Adressierung verwendet werden.  
  
## <a name="web-farm-attacker-replays-request-to-multiple-nodes"></a>Webfarm: Angreifer Wiederholen von Anforderungen an mehreren Knoten  
 Ein Client verwendet einen Dienst, der in einer Webfarm implementiert ist. Ein Angreifer wiederholt eine Anforderung, die an einen Knoten in der Farm gesendet wurde, für einen anderen Knoten in der Farm. Zusätzlich wird beim Neustart eines Diensts der Wiederholungscache geleert, sodass der Angriff wiederholt werden kann. (Der Cache enthält die bereits verwendeten Signaturen von Nachrichten und verhindert so, dass diese mehrfach verwendet werden können. Wiederholungscaches werden nicht von mehreren Anwendungen in einer Webfarm verwendet.)  
  
 Mögliche Entschärfungen:  
  
-   Verwenden Sie die Nachrichtenmodussicherheit mit zustandsbehafteten Token für den Sicherheitskontext (mit oder ohne sichere Konversation). Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie einen Sicherheitskontext für eine sichere Sitzung Token](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
-   Konfigurieren Sie den Dienst für die Sicherheit auf Transportebene.  
  
## <a name="see-also"></a>Siehe auch

- [Sicherheitsüberlegungen](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)
- [Veröffentlichung von Informationen](../../../../docs/framework/wcf/feature-details/information-disclosure.md)
- [Angriffe durch Rechteerweiterung](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)
- [Dienstverweigerung (Denial of Service)](../../../../docs/framework/wcf/feature-details/denial-of-service.md)
- [Verfälschungen](../../../../docs/framework/wcf/feature-details/tampering.md)
- [Nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
