---
title: "Erweiterungen der Socketleistung in Version 3.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 225aa5f9-c54b-4620-ab64-5cd100cfd54c
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Erweiterungen der Socketleistung in Version 3.5
Die <xref:System.Net.Sockets.Socket?displayProperty=fullName>\-Klasse ist in Version 3.5 für Anwendungen verbessert, die asynchrone Netzwerk\-E\/A verwenden, um die höchste Leistung zu erzielen.  Eine neue Klassen sind als Teil eines Satzes Erweiterungen zur <xref:System.Net.Sockets.Socket>\-Klasse hinzugefügt, die einen alternativen asynchrone Muster an, das durch spezialisierte leistungsstarke Socket\-Anwendungen verwendet werden kann.  Diese Erweiterungen wurden speziell für Netzwerkserver\-Anwendungen entwickelt, die hohe Leistungsfähigkeit erfordern.  Eine Anwendung kann das erweiterte asynchrone Muster oder nur in bestimmten Bereichen aktiven ihrer Anwendung ausschließlich verwenden \(wenn große Datenmengen, beispielsweise empfangen werden\).  
  
## Klassen\-Erweiterungen  
 Das Hauptfeature dieser Erweiterungen ist das Vermeiden des wiederholten Zuweisens und Synchronisierens von Objekten bei asynchronen E\/A\-Socketvorgängen mit großem Volumen.  Das Muster des mit paarweisen Begin\/Endenentwurfs, das gerade durch die <xref:System.Net.Sockets.Socket>\-Klasse für asynchrone E\/A Socket implementiert wird, benötigt ein <xref:System.IAsyncResult?displayProperty=fullName>\-Objekt zugeordnet wird für jeden asynchronen Socketvorgang.  
  
 In den neuen <xref:System.Net.Sockets.Socket>\-Klassenerweiterungen werden asynchrone Socketvorgänge durch wiederverwendbare <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=fullName>\-Klassenobjekte beschrieben, die von der Anwendung zugeordnet werden und gespeichert sind.  Leistungsstarke Socketanwendungen kennen die Menge an überlappenden Socketvorgängen, die aufrechterhalten werden müssen, am besten.  Die Anwendung kann so viele <xref:System.Net.Sockets.SocketAsyncEventArgs>\-Objekte wie benötigt erstellen.  Wenn beispielsweise eine Serveranwendung Socket 15 die Operationen jederzeit akzeptieren können muss, die, um eingehende Client\-Verbindungskinetik zu unterstützen ausstehend sind, kann sie 15 wiederverwendbare <xref:System.Net.Sockets.SocketAsyncEventArgs>\-Objekte zu diesem Zweck im Voraus zuordnen.  
  
 Das Muster zum Ausführen eines asynchronen Socketvorgangs mit dieser Klasse besteht aus den folgenden Schritten:  
  
1.  Zuweisen eines neuen <xref:System.Net.Sockets.SocketAsyncEventArgs>\-Kontextobjekts oder Abrufen eines freien Objekts aus einem Anwendungspool.  
  
2.  Legen Sie Eigenschaften auf dem Kontextobjekt der ausgeführt werden soll, etwa Operation fest \(die Rückrufdelegatmethode und \-Datenpuffer\).  
  
3.  Aufrufen der entsprechenden Socketmethode \(xxxAsync\), um den asynchronen Vorgang zu initiieren.  
  
4.  Wenn das asynchrone true der Socketmethode \(xxxAsync\) im Rückruf, die Kontexteigenschaften für Abschlussstatus abfragen.  
  
5.  Wenn die asynchrone Socketmethode \(xxxAsync\) im Rückruf false zurückgibt, der Vorgang synchron abgeschlossen.  Das Ergebnis des Vorgangs kann in den Kontexteigenschaften abgefragt werden.  
  
6.  Wiederverwenden des Kontexts für einen anderen Vorgang, Zurückgeben an den Pool oder Verwerfen.  
  
 Die Lebensdauer des neuen asynchronen Socketvorgangskontextobjekts wird durch Verweise im Anwendungscode und asynchronen in der E\/A\-Verweisen bestimmt.  Die Anwendung muss keinen Verweis auf ein Kontextobjekt für asynchrone Socketvorgänge beibehalten, wenn es als Parameter an eine der Methoden für asynchrone Socketvorgänge übergeben wurde.  Der Verweis bleibt erhalten, bis der Abschlussrückruf zurückgegeben wird.  Allerdings ist es günstig, damit die Anwendung den Verweis auf das Kontextobjekt beibehält, sodass sie für einen zukünftigen asynchronen Socketvorgang wiederverwendet werden kann.  
  
## Siehe auch  
 <xref:System.Net.Sockets.Socket?displayProperty=fullName>   
 <xref:System.Net.Sockets.SendPacketsElement?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketAsyncOperation?displayProperty=fullName>   
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Socket\-Leistungs\-Technologie\-Beispiel](http://go.microsoft.com/fwlink/?LinkID=179570)