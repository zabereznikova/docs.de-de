---
title: Erweiterungen der Socketleistung in Version 3.5
ms.date: 03/30/2017
ms.assetid: 225aa5f9-c54b-4620-ab64-5cd100cfd54c
ms.openlocfilehash: 577c033fc5639f9d9f50e413fd2cb55a75d48f2c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047243"
---
# <a name="socket-performance-enhancements-in-version-35"></a>Erweiterungen der Socketleistung in Version 3.5
Die <xref:System.Net.Sockets.Socket?displayProperty=nameWithType>-Klasse wurde in Version 3.5 für die Verwendung von Anwendungen verbessert, die asynchrone Netzwerk-E/A verwenden, um die höchste Leistung zu erreichen. Es wurde eine Serie neuer Klassen als Teil eines Satzes von Ergänzungen für die <xref:System.Net.Sockets.Socket>-Klasse hinzugefügt, durch die ein alternatives asynchrones Muster bereitgestellt wird, das von spezialisierten Socketanwendungen mit hoher Leistung verwendet werden kann. Diese Verbesserungen wurden speziell für Netzwerkserveranwendungen entwickelt, die hohe Leistung erfordern. Eine Anwendung kann die erweiterten asynchronen Muster ausschließlich oder nur in bestimmten Bereichen ihrer Anwendung nutzen (wenn z.B. große Datenmengen empfangen werden).  
  
## <a name="class-enhancements"></a>Klassenverbesserungen  
 Die Hauptfunktion dieser Erweiterungen ist die Vermeidung der wiederholten Zuordnung und Synchronisierung von Objekten während asynchroner Socket-E/A mit hohem Volumen. Das derzeit von der <xref:System.Net.Sockets.Socket>-Klasse für asynchrone Socket-E/A implementierte Begin/End-Entwurfsmuster erfordert, dass jedem asynchronen Socketvorgang ein <xref:System.IAsyncResult?displayProperty=nameWithType>-Objekt zugewiesen wird.  
  
 In den neuen <xref:System.Net.Sockets.Socket>-Klassenerweiterungen werden asynchrone Vorgänge von wiederverwendbaren <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=nameWithType>-Klassenobjekten beschrieben, die von der Anwendung zugewiesen und verwaltet werden. Socketanwendungen mit hoher Leistung kennen die Menge an überlappenden Socketvorgängen, die aufrechterhalten werden müssen, am besten. Die Anwendung kann so viele <xref:System.Net.Sockets.SocketAsyncEventArgs>-Objekte erstellen wie nötig. Wenn beispielsweise eine Serveranwendung zu jeder Zeit 15 Socketannahmevorgänge zur Verfügung haben muss, um eingehende Clientverbindungsraten zu unterstützen, kann sie diesem Zweck im Voraus 15 wiederverwendbare <xref:System.Net.Sockets.SocketAsyncEventArgs>-Objekte zuweisen.  
  
 Das Muster zum Ausführen eines asynchronen Socketvorgangs mit dieser Klasse besteht aus den folgenden Schritten:  
  
1. Zuweisen eines neuen <xref:System.Net.Sockets.SocketAsyncEventArgs>-Kontextobjekt oder Abrufen eines kostenlosen aus einem Anwendungspool.  
  
2. Festlegen von Eigenschaften für das Kontextobjekt für den durchzuführenden Vorgang (z.B. die Methode des Rückrufdelegaten und Datenpuffers).  
  
3. Aufrufen der entsprechenden Socketmethode (XxxAsync) zum Initiieren des asynchronen Vorgangs.  
  
4. Wenn die asynchrone Socketmethode (XxxAsync) im Rückruf TRUE zurückgibt, dann fragen Sie die Kontexteigenschaften für den Abschlussstatus ab.  
  
5. Wenn die asynchrone Socketmethode (XxxAsync) im Rückruf FALSE zurückgibt, wurde der Vorgang synchron abgeschlossen. Die Kontexteigenschaften könnten möglicherweise für das Betriebsergebnis abgefragt werden.  
  
6. Verwenden Sie den Kontext für einen anderen Vorgang erneut, fügen Sie ihn wieder in den Pool ein, oder verwerfen Sie ihn.  
  
 Die Lebensdauer des neuen Kontextobjekts des asynchronen Socketvorgangs wird durch Verweise im Anwendungscode und asynchrone E/A-Verweise bestimmt. Es ist nicht erforderlich, dass die Anwendung einen Verweis auf das Kontextobjekt des asynchronen Socketvorgangs beibehält, nachdem er als Parameter an eine der Methoden des asynchronen Socketvorgangs gesendet wurde. Der Verweis bleibt bestehen, bis der Abschlussrückruf zurückgegeben wird. Es ist jedoch von Vorteil für die Anwendung, den Verweis auf das Kontextobjekt beizubehalten, damit er für einen weiteren asynchronen Socketvorgang wiederverwendet werden kann.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.Sockets.Socket?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SendPacketsElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketAsyncOperation?displayProperty=nameWithType>
- [Network Programming Samples (Beispiele zur Netzwerkprogrammierung)](network-programming-samples.md)
- [Socketcodebeispiele](socket-code-examples.md)
