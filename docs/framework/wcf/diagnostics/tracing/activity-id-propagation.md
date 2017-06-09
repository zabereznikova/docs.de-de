---
title: "Weitergabe der Aktivit&#228;ts-ID | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cd1c1ae5-cc8a-4f51-90c9-f7b476bcfe70
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Weitergabe der Aktivit&#228;ts-ID
Die Weitergabe erfolgt, wenn die ServiceModel\-Aktivitätsablaufverfolgung aktiviert \(ServiceModel\-Weitergabe\) oder deaktiviert \(Benutzer\-zu\-Benutzer\-Aktivitätsweitergabe\) ist.  
  
## ServiceModel\-Aktivitätsablaufverfolgung ist aktiviert  
 Wenn die ServiceModel\-Aktivitätsablaufverfolgung aktiviert ist, erfolgt die Weitergabe zwischen ProcessAction\-Aktivitäten.  
  
### Server  
 Wenn das `propagateActivity` \-Attribut auf dem Client und auf dem Server auf `true` festgelegt ist, ist die ID der `ProcessAction`\-Aktivität auf dem Server identisch mit der ID im weitergegebenen `ActivityId`\-Nachrichtenheader.  
  
 Wenn in der  Nachricht kein `ActivityId`\-Header vorhanden ist \(d. h. auf dem Client ist `propagateActivity`\=`false`\), oder wenn auf dem Server `propagateActivity`\=`false` ist, generiert der Server eine neue Aktivitäts\-ID.  
  
### Client  
 Wenn der Client ein synchroner Singlethread\-Client ist, ignoriert er alle Einstellungen von `propagateActivity` auf dem Client oder Server.  Stattdessen wird die Antwort in der Anforderungsaktivität behandelt.  Wenn der Client ein asynchroner oder synchroner Multithread\-Client ist, auf dem Client `propagateActivity`\=`true` ist und ein Aktivitäts\-ID\-Header in der vom Server gesendeten Nachricht vorhanden ist, ruft der Client die Aktivitäts\-ID aus der Nachricht ab und überträgt zur ProcessAction\-Aktivität, die die weitergegebene Aktivitäts\-ID enthält.  Andernfalls überträgt der Client aus der ProcessMessage\-Aktivität zu einer neuen ProcessAction\-Aktivität.  Diese zusätzliche Übertragung zu einer neuen ProcessAction\-Aktivität erfolgt im Hinblick auf die Konsistenz.  Innerhalb dieser Aktivität ruft der Client die Aktivitäts\-ID der BeginCall\-Aktivität aus dem lokalen Threadkontext ab, wenn der Thread für die Verarbeitung der Antwortnachricht reserviert wird.  Er überträgt dann zur ursprünglichen ProcessAction\-Aktivität.  
  
 Wenn der Client ein Duplexclient ist, fungiert der Client beim Empfangen der Nachricht als Server.  
  
### Weitergabe in Fehlermeldungen  
 Es gibt keinen Unterschied bei der Behandlung von gültigen Meldungen und Fehlermeldungen.  Wenn `propagateActivity`\=`true` ist, ist die zu den SOAP\-Fehlermeldungs\-Headern hinzugefügte Aktivitäts\-ID identisch mit der Umgebungsaktivität.  
  
## ServiceModel\-Aktivitätsablaufverfolgung ist deaktiviert  
 Wenn die ServiceModel\-Aktivitätsablaufverfolgung deaktiviert ist, erfolgt die Weitergabe direkt zwischen Benutzercodeaktivitäten ohne Durchlaufen von ServiceModel\-Aktivitäten.  Eine benutzerdefinierte Aktivitäts\-ID wird auch durch den Nachrichtenaktivitäts\-ID\-Header weitergegeben.  
  
 Wenn für einen ServiceModel\-Ablaufverfolgungslistener `propagateActivity`\=`true` und `ActivityTracing`\=`off` ist \(unabhängig davon, ob die Ablaufverfolgung für ServiceModel aktiviert ist \), tritt entweder auf dem Client oder dem Server das folgende Ereignis auf:  
  
-   Bei einer Vorgangsanforderung oder beim Senden von Antworten wird die Aktivitäts\-ID im TLS aus Benutzercode weitergegeben, bis eine Nachricht erstellt wird.  Außerdem wird ein Aktivitäts\-ID\-Header in die Nachricht eingefügt, bevor sie gesendet wird.  
  
-   Beim Empfangen einer Anforderung oder einer Antwort wird die Aktivitäts\-ID aus dem Nachrichtenheader abgerufen, sobald das empfangene Nachrichtenobjekt erstellt wird.  Die Aktivitäts\-ID im TLS wird weitergegeben, sobald die Nachricht nicht mehr im Bereich angezeigt wird, bis Benutzercode erreicht wird.  
  
 Diese Aktionen garantieren, dass Benutzerablaufverfolgungen in der gleichen Aktivität angezeigt werden, wenn die Weitergabe aktiviert ist.  ServiceModel\-Ablaufverfolgungen sind jedoch nicht garantiert.  ServiceModel\-Ablaufverfolgungen treten in einer Benutzercodeaktivität nur dann auf, wenn die Verarbeitung dieser Ablaufverfolgungen auf dem gleichen Thread erfolgt, auf dem die Benutzercodeaktivität festgelegt wurde.  
  
 Im Allgemeinen können ServiceModel\-Ablaufverfolgungen an den folgenden Stellen beobachtet werden:  
  
-   Wenn die ServiceModel\-Ablaufverfolgung deaktiviert ist, werden alle ausgegebenen Ablaufverfolgungen in Benutzeraktivitäten angezeigt.  Wenn die Weitergabe auf dem Server und auf dem Client aktiviert ist, befinden sich diese Ablaufverfolgungen in der gleichen Aktivität.  
  
-   Ist die ServiceModel\-Ablaufverfolgung aktiviert, die Aktivitätsablaufverfolgung jedoch deaktiviert, werden Benutzerablaufverfolgungen in der gleichen Aktivität angezeigt, wenn die Weitergabe an beiden Enden aktiviert ist.  ServiceModel\-Ablaufverfolgungen werden in der standardmäßigen Aktivität "0000" angezeigt, wenn sie sich nicht auf dem gleichen Thread wie die Benutzercodeverarbeitung befinden, auf dem die Aktivität ursprünglich festgelegt wurde.  
  
-   Wenn sowohl die ServiceModel\-Ablaufverfolgung als auch die Aktivitätsablaufverfolgung aktiviert ist, werden Benutzerablaufverfolgungen in benutzerdefinierten Aktivitäten angezeigt, und ServiceModel\-Ablaufverfolgungen werden in vom ServiceModel definierten Aktivitäten angezeigt.  Die Weitergabe erfolgt auf ServiceModel\-Ebene.