---
title: Weitergabe der Aktivitäts-ID
ms.date: 03/30/2017
ms.assetid: cd1c1ae5-cc8a-4f51-90c9-f7b476bcfe70
ms.openlocfilehash: 0f0478b16bf2ca0975ae0290a8855756ecfc383e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236103"
---
# <a name="activity-id-propagation"></a>Weitergabe der Aktivitäts-ID

Die Weitergabe erfolgt, wenn die ServiceModel-Aktivitätsablaufverfolgung aktiviert (ServiceModel-Weitergabe) oder deaktiviert (Benutzer-zu-Benutzer-Aktivitätsweitergabe) ist.  
  
## <a name="servicemodel-activity-tracing-is-enabled"></a>ServiceModel-Aktivitätsablaufverfolgung ist aktiviert  

 Wenn die ServiceModel-Aktivitätsablaufverfolgung aktiviert ist, erfolgt die Weitergabe zwischen ProcessAction-Aktivitäten.  
  
### <a name="server"></a>Server  

 Wenn das `propagateActivity` `true` -Attribut sowohl auf dem Client als auch auf dem Server auf festgelegt ist, ist die ID der `ProcessAction` Aktivität auf dem Server mit der ID im propagierten `ActivityId` Nachrichten Header identisch.  
  
 Wenn kein `ActivityId` Header in der Nachricht vorhanden ist (d. h. `propagateActivity` = `false` auf dem Client) oder wenn `propagateActivity` = `false` auf dem Server, generiert der Server eine neue Aktivitäts-ID.  
  
### <a name="client"></a>Client  

 Wenn der Client ein synchroner Singlethread-Client ist, ignoriert er alle Einstellungen von `propagateActivity` auf dem Client oder Server. Stattdessen wird die Antwort in der Anforderungsaktivität behandelt. Wenn der Client asynchron oder synchron Multithreaded ist, `propagateActivity` = `true` auf dem Client und ein Aktivitäts-ID-Header in der vom Server gesendeten Nachricht vorhanden ist, ruft der Client die Aktivitäts-ID aus der Nachricht ab und überträgt sie an die Prozess Aktions Aktivität, die die propagierte Aktivitäts-ID enthält. Andernfalls überträgt der Client aus der ProcessMessage-Aktivität zu einer neuen ProcessAction-Aktivität. Diese zusätzliche Übertragung zu einer neuen ProcessAction-Aktivität erfolgt im Hinblick auf die Konsistenz. Innerhalb dieser Aktivität ruft der Client die Aktivitäts-ID der BeginCall-Aktivität aus dem lokalen Threadkontext ab, wenn der Thread für die Verarbeitung der Antwortnachricht reserviert wird. Er überträgt dann zur ursprünglichen ProcessAction-Aktivität.  
  
 Wenn der Client ein Duplexclient ist, fungiert der Client beim Empfangen der Nachricht als Server.  
  
### <a name="propagation-in-fault-messages"></a>Weitergabe in Fehlermeldungen  

 Es gibt keinen Unterschied bei der Behandlung von gültigen Meldungen und Fehlermeldungen. `propagateActivity` = `true` Gibt an, dass die dem SOAP-Fehlermeldungs Header hinzugefügte Aktivitäts-ID mit der Ambient-Aktivität identisch ist.  
  
## <a name="servicemodel-activity-tracing-is-disabled"></a>ServiceModel-Aktivitätsablaufverfolgung ist deaktiviert  

 Wenn die ServiceModel-Aktivitätsablaufverfolgung deaktiviert ist, erfolgt die Weitergabe direkt zwischen Benutzercodeaktivitäten ohne Durchlaufen von ServiceModel-Aktivitäten. Eine benutzerdefinierte Aktivitäts-ID wird auch durch den Nachrichtenaktivitäts-ID-Header weitergegeben.  
  
 Wenn und für einen Service Model-Ablaufverfolgungslistener `propagateActivity` = `true` `ActivityTracing` = `off` (unabhängig davon, ob die Ablauf Verfolgung für Service Model aktiviert ist), geschieht Folgendes auf dem Client oder auf dem Server:  
  
- Bei einer Vorgangsanforderung oder beim Senden von Antworten wird die Aktivitäts-ID im TLS aus Benutzercode weitergegeben, bis eine Nachricht erstellt wird. Außerdem wird ein Aktivitäts-ID-Header in die Nachricht eingefügt, bevor sie gesendet wird.  
  
- Beim Empfangen einer Anforderung oder einer Antwort wird die Aktivitäts-ID aus dem Nachrichtenheader abgerufen, sobald das empfangene Nachrichtenobjekt erstellt wird. Die Aktivitäts-ID im TLS wird weitergegeben, sobald die Nachricht nicht mehr im Bereich angezeigt wird, bis Benutzercode erreicht wird.  
  
 Diese Aktionen garantieren, dass Benutzerablaufverfolgungen in der gleichen Aktivität angezeigt werden, wenn die Weitergabe aktiviert ist. ServiceModel-Ablaufverfolgungen sind jedoch nicht garantiert. ServiceModel-Ablaufverfolgungen treten in einer Benutzercodeaktivität nur dann auf, wenn die Verarbeitung dieser Ablaufverfolgungen auf dem gleichen Thread erfolgt, auf dem die Benutzercodeaktivität festgelegt wurde.  
  
 Im Allgemeinen können ServiceModel-Ablaufverfolgungen an den folgenden Stellen beobachtet werden:  
  
- Wenn die ServiceModel-Ablaufverfolgung deaktiviert ist, werden alle ausgegebenen Ablaufverfolgungen in Benutzeraktivitäten angezeigt. Wenn die Weitergabe auf dem Server und auf dem Client aktiviert ist, befinden sich diese Ablaufverfolgungen in der gleichen Aktivität.  
  
- Ist die ServiceModel-Ablaufverfolgung aktiviert, die Aktivitätsablaufverfolgung jedoch deaktiviert, werden Benutzerablaufverfolgungen in der gleichen Aktivität angezeigt, wenn die Weitergabe an beiden Enden aktiviert ist. ServiceModel-Ablaufverfolgungen werden in der standardmäßigen Aktivität "0000" angezeigt, wenn sie sich nicht auf dem gleichen Thread wie die Benutzercodeverarbeitung befinden, auf dem die Aktivität ursprünglich festgelegt wurde.  
  
- Wenn sowohl die ServiceModel-Ablaufverfolgung als auch die Aktivitätsablaufverfolgung aktiviert ist, werden Benutzerablaufverfolgungen in benutzerdefinierten Aktivitäten angezeigt, und ServiceModel-Ablaufverfolgungen werden in vom ServiceModel definierten Aktivitäten angezeigt. Die Weitergabe erfolgt auf ServiceModel-Ebene.
