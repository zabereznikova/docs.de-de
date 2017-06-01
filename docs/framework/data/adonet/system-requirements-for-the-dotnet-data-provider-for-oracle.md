---
title: "Systemanforderungen f&#252;r den.NET Framework-Datenanbieter f&#252;r Oracle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 054f76b9-1737-43f0-8160-84a00a387217
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Systemanforderungen f&#252;r den.NET Framework-Datenanbieter f&#252;r Oracle
Der .NET Framework\-Datenanbieter für Oracle erfordert Microsoft Data Access Components \(MDAC\), Version 2.6 oder höher.  MDAC 2.8 mit SP1 wird empfohlen.  
  
 Ebenso muss der Oracle 8i\-Client, Version 3 \(8.1.7\) oder höher, installiert sein.  
  
 Oracle Clientsoftware, die älter als Version Oracle 9i ist, kann nicht auf UTF16\-Datenbanken zugreifen, weil UTF16 eine neue Funktion in Oracle 9i ist.  Wenn Sie diese Funktion verwenden möchten, müssen Sie die Clientsoftware auf Oracle 9i oder höher aktualisieren.  
  
## Arbeiten mit dem Datenanbieter für Oracle\- und Unicode\-Daten  
 Es folgt eine Liste von Unicode\-relevanten Themen, die Sie bei der Arbeit mit dem .NET Framework\-Datenanbieter für Oracle und Oracle\-Clientbibliotheken berücksichtigen sollten.  Weitere Informationen finden Sie in der Oracle\-Dokumentation.  
  
### Festlegen des Unicode\-Werts in einem Verbindungszeichenfolgen\-Attribut  
 Beim Arbeiten mit Oracle können Sie das Verbindungszeichenfolgen\-Attribut  
  
```  
Unicode=True   
```  
  
 verwenden, um die Oracle\-Clientbibliotheken im UTF\-16\-Modus zu initialisieren.  Dadurch müssen die Oracle\-Clientbibliotheken UTF\-16\-Zeichenfolgen \(die UCS\-2 sehr ähnlich sind\) anstelle von Multi\-Byte\-Zeichenfolgen akzeptieren.  Der Datenanbieter für Oracle kann somit immer eine beliebigen Oracle\-Codepage ohne zusätzliche Umwandlungen verwenden.  Diese Konfiguration funktioniert nur, wenn Oracle 9i\-Clients für die Kommunikation mit einer Oracle 9i\-Datenbank mit dem alternativen Zeichensatz AL16UTF16 verwendet werden.  Bei der Kommunikation eines Oracle 9i\-Client mit einem Oracle 9i\-Server sind zusätzliche Ressourcen erforderlich, um die **CommandText**\-Unicodewerte in den entsprechenden Multi\-Byte\-Zeichensatz umzuwandeln, der vom Oracle9i Server verwendet wird.  Durch Hinzufügen von `Unicode=True` zur Verbindungszeichenfolge kann dies vermieden werden, wenn Sie über eine sichere Konfiguration verfügen.  
  
### Verwenden verschiedener Versionen von Oracle Client und Oracle Server  
 Oracle 8i\-Clients können nicht auf **NCHAR**\-, **NVARCHAR2**\- oder **NCLOB**\-Daten in Oracle 9i\-Datenbanken zugreifen, wenn der nationale Zeichensatz des Servers als AL16UTF16 \(die Standardeinstellung für Oracle 9i\) angegeben ist.  Da die Unterstützung für den UTF\-16\-Zeichensatz erst ab Oracle 9i eingeführt wurde, können Oracle 8i\-Clients ihn nicht lesen.  
  
### Arbeiten mit UTF\-8\-Daten  
 Wenn Sie den alternativen Zeichensatz festlegen möchten, legen Sie den Registrierungsschlüssel HKEY\_LOCAL\_MACHINE\\SOFTWARE\\ORACLE\\HOMEID\\NLS\_LANG auf UTF8 fest.  Weitere Informationen finden Sie in den Oracle\-Installationshinweisen für Ihre Plattform.  Die Standardeinstellung ist der primäre Zeichensatz der Sprache, in der Sie die Oracle Clientsoftware installieren.  Wenn Sie die Sprache nicht entsprechend dem Zeichensatz der Landessprache für die Datenbank festlegen, mit der Sie die Verbindung herstellen, führt dies dazu, dass die Parameter\- und Spaltenbindungen Daten im primären Zeichensatz der Datenbank und nicht im nationalen Zeichensatz senden oder empfangen.  
  
### OracleLob kann nur vollständige Zeichen aktualisieren.  
 Aus Gründen der Verwendbarkeit erbt das <xref:System.Data.OracleClient.OracleLob>\-Objekt von der .NET Framework\-Streamklasse und stellt die **ReadByte**\-Methode und die **WriteByte**\-Methode bereit.  Es implementiert auch Methoden, z. B. **CopyTo** und **Erase**, die Abschnitte von Oracle\-**LOB**\-Objekten verarbeiten.  Im Unterschied dazu stellt die Oracle Clientsoftware mehrere APIs für die Arbeit mit Zeichen\-**LOBs** \(**CLOB** und **NCLOB**\) bereit.  Allerdings unterstützen diese APIs nur vollständige Zeichen.  Aufgrund dieses Unterschieds implementiert der Datenanbieter für Oracle die Unterstützung für **Read** und **ReadByte**, damit UTF\-16\-Daten byteweise verarbeitet werden können.  Die anderen Methoden des **OracleLob**\-Objekts ermöglichen jedoch nur Operationen für vollständige Zeichen.  
  
## Siehe auch  
 [Oracle und ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)