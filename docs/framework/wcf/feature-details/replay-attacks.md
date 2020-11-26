---
title: Wiederholungsangriffe
ms.date: 03/30/2017
ms.assetid: 7a17e040-93cd-4432-81b9-9f62fec78c8f
ms.openlocfilehash: 4325b3747074f13cf02752f99b25fa02e4117b4c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239080"
---
# <a name="replay-attacks"></a>Wiederholungsangriffe

Ein *Replay-Angriff* tritt auf, wenn ein Angreifer einen Nachrichtenstrom zwischen zwei Parteien kopiert und den Datenstrom für eine oder mehrere der Parteien wieder gibt. Wenn der Angriff nicht abgeschwächt wird, verarbeiten die angegriffenen Computer den Stream wie zulässige Nachrichten, was eine Reihe negativer Konsequenzen wie redundante Bestellungen eines Artikels zur Folge hat.  
  
## <a name="bindings-may-be-subject-to-reflection-attacks"></a>Bindungen sind möglicherweise Reflektionsangriffen ausgesetzt  

 *Reflektionsangriffe* werden Nachrichten zurück an einen Absender wiedergeben, als ob Sie vom Empfänger als Antwort empfangen wurden. Die Standard *Wiedergabe Erkennung* im Windows Communication Foundation (WCF)-Mechanismus behandelt dies nicht automatisch.  
  
 Reflektionsangriffe werden standardmäßig gemindert, da das WCF-Dienstmodell eine signierte Meldungs-ID zum Anfordern von Nachrichten hinzufügt und einen signierten `relates-to` Header für Antwort Nachrichten erwartet. Infolgedessen kann die Anforderungsnachricht nicht als Antwort wiederholt werden. In sicheren Szenarien mit zuverlässigem Messaging werden Reflektionsangriffe aus folgenden Gründen abgemildert:  
  
- Die Sequenzerstellung und die Sequenzerstellungsantwort verwenden unterschiedliche Nachrichtenschemas.  
  
- Bei Simplexsequenzen können die vom Client gesendeten Nachrichten nicht wiedergegeben werden, da diese vom Client nicht interpretiert werden können.  
  
- Bei Duplexsequenzen müssen die beiden Sequenzkennungen eindeutig sein. Ausgehende Nachrichten können daher nicht als eingehende Nachrichten wiederholt werden (alle Header und Texte werden ebenfalls signiert).  
  
 Aus diesem Grund sind nur Bindungen ohne WS-Adressierung anfällig für Reflektionsangriffe: benutzerdefinierte Bindungen, deren WS-Adressierung deaktiviert ist und die mit symmetrischen Schlüsseln gesichert sind. Die <xref:System.ServiceModel.BasicHttpBinding> verwendet standardmäßig keine WS-Adressierung; die Absicherung durch symmetrische Schlüssel erfolgt jedoch auf eine Art und Weise, die sie anfällig gegenüber dieser Art von Angriffen macht.  
  
 Zur Entschärfung für benutzerdefinierte Bindungen sollte auf einen Sicherheitskontext verzichtet werden, oder es sollten Header für die WS-Adressierung verwendet werden.  
  
## <a name="web-farm-attacker-replays-request-to-multiple-nodes"></a>Webfarm: Angriff durch Wiederholen von Anforderungen an mehrere Knoten  

 Ein Client verwendet einen Dienst, der in einer Webfarm implementiert ist. Ein Angreifer wiederholt eine Anforderung, die an einen Knoten in der Farm gesendet wurde, für einen anderen Knoten in der Farm. Zusätzlich wird beim Neustart eines Diensts der Wiederholungscache geleert, sodass der Angriff wiederholt werden kann. (Der Cache enthält die bereits verwendeten Signaturen von Nachrichten und verhindert so, dass diese mehrfach verwendet werden können. Wiederholungscaches werden nicht von mehreren Anwendungen in einer Webfarm verwendet.)  
  
 Mögliche Entschärfungen:  
  
- Verwenden Sie die Nachrichtenmodussicherheit mit zustandsbehafteten Token für den Sicherheitskontext (mit oder ohne sichere Konversation). Weitere Informationen finden Sie unter Vorgehens [Weise: Erstellen eines Sicherheitskontext Tokens für eine sichere Sitzung](how-to-create-a-security-context-token-for-a-secure-session.md).  
  
- Konfigurieren Sie den Dienst für die Sicherheit auf Transportebene.  
  
## <a name="see-also"></a>Weitere Informationen

- [Sicherheitshinweise](security-considerations-in-wcf.md)
- [Veröffentlichung von Informationen](information-disclosure.md)
- [Erhöhung von Rechten](elevation-of-privilege.md)
- [Denial-of-Service](denial-of-service.md)
- [Manipulation](tampering.md)
- [Nicht unterstützte Szenarien](unsupported-scenarios.md)
