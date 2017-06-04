---
title: "Sch&#252;tzen von Verbindungsinformationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1471f580-bcd4-4046-bdaf-d2541ecda2f4
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Sch&#252;tzen von Verbindungsinformationen
Eines der wichtigsten Ziele beim Sichern einer Anwendung besteht darin, den Zugriff auf die Datenquelle zu schützen.  Eine Verbindungszeichenfolge stellt ein potenzielles Sicherheitsrisiko dar, wenn sie nicht gesichert wird.  Das Speichern von Verbindungsinformationen als Klartext oder das Aufbewahren dieser Informationen im Arbeitsspeicher gefährdet Ihr gesamtes System.  Die in Ihrem Quellcode eingebetteten Verbindungszeichenfolgen können mit dem [Ildasm.exe \(IL Disassembler\)](../../../../docs/framework/tools/ildasm-exe-il-disassembler.md) gelesen werden, um so MSIL \(Microsoft Intermediate Language\) in einer kompilierten Assembly anzuzeigen.  
  
 Welche Sicherheitsrisiken sich im Zusammenhang mit Verbindungszeichenfolgen ergeben, hängt von der Art der verwendeten Authentifizierung, der Art und Weise, wie die Verbindungszeichenfolgen im Arbeitsspeicher und auf der Festplatte aufbewahrt werden, und den Verfahren ab, mit denen die Verbindungszeichenfolgen zur Laufzeit konstruiert werden.  
  
## Verwenden Sie die Windows\-Authentifizierung.  
 Damit der Zugriff auf die Datenquelle geschützt bleibt, müssen Sie Verbindungsinformationen wie Benutzer\-ID, Kennwort und den Namen der Datenquelle sichern.  Um zu vermeiden, dass Benutzerinformationen verfügbar gemacht werden, empfehlen wir überall, wo es möglich ist, die Windows\-Authentifizierung \(auch als *integrierte Sicherheit* bezeichnet\) zu verwenden.  Die Windows\-Authentifizierung wird in einer Verbindungszeichenfolge mit dem Schlüsselwort `Integrated Security` oder `Trusted_Connection` angegeben, sodass weder eine Benutzer\-ID noch ein Kennwort verwendet werden muss.  Bei Verwendung der Windows\-Authentifizierung werden die Benutzer von Windows authentifiziert, und der Zugriff auf Server\- und Datenbankressourcen wird durch die Erteilung von Berechtigungen für Windows\-Benutzer und \-Gruppen gesteuert.  
  
 Dort, wo die Windows\-Authentifizierung nicht verwendet werden kann, müssen Sie besondere Vorsicht walten lassen, da die Verbindungszeichenfolge Benutzeranmeldeinformationen enthält, die offen zugänglich sind.  In ASP.NET\-Anwendungen können Sie ein Windows\-Konto als feste Identität konfigurieren, die dann für Verbindungen mit Datenbanken und anderen Netzwerkressourcen verwendet wird.  Sie aktivieren im Identitätselement in der Datei **web.config** den Identitätswechsel und geben einen Benutzernamen und ein Kennwort an.  
  
```  
<identity impersonate="true"   
        userName="MyDomain\UserAccount"   
        password="*****" />  
```  
  
 Das Konto mit der festen Identität sollte nur über die nötigsten Berechtigungen für die Datenbank verfügen.  Außerdem sollten Sie die Konfigurationsdatei verschlüsseln, sodass der Benutzername und das Kennwort nicht als Klartext verfügbar gemacht werden.  
  
## Verwenden Sie keine UDL\-Dateien \(Universal Data Link\)  
 Vermeiden Sie, Verbindungszeichenfolgen für eine <xref:System.Data.OleDb.OleDbConnection> in einer UDL\-Datei \(Universal Data Link, universelle Datenverknüpfung\) zu speichern.  Informationen in UDLs werden in Klartext gespeichert und können nicht verschlüsselt werden.  Bei einer UDL\-Datei handelt es sich um eine externe dateibasierte Ressource der Anwendung, die mit .NET Framework nicht gesichert oder verschlüsselt werden kann.  
  
## Vermeiden von Einfügeangriffen mit Verbindungszeichenfolgen\-Generatoren  
 Zu einem Angriff durch Einschleusen von Verbindungszeichenfolgen kann es kommen, wenn die dynamische Zeichenfolgenverkettung verwendet wird, um auf Benutzereingabe basierende Verbindungszeichenfolgen zu konstruieren.  Wenn die Benutzereingabe nicht validiert wird und schädlicher Text \(oder schädliche Zeichen\) nicht maskiert wird, kann ein Angreifer möglicherweise auf sicherheitsrelevante Daten oder andere Ressourcen auf dem Server zugreifen.  Zur Vermeidung dieses Problems enthält ADO.NET 2.0 neue Verbindungszeichenfolgen\-Generatorklassen, mit deren Hilfe die Verbindungszeichenfolgensyntax validiert und sichergestellt werden kann, dass keine zusätzlichen Parameter eingeschleust werden.  Weitere Informationen finden Sie unter [Verbindungszeichenfolgen\-Generatoren](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
## Verwenden von "Persist Security Info\=False"  
 Die Standardeinstellung für `Persist Security Info` ist false. Wir empfehlen, diesen Standardwert in allen Verbindungszeichenfolgen beizubehalten.  Wenn Sie `Persist Security Info` auf `true` oder `yes` festlegen, können sicherheitsrelevante Informationen, wie die Benutzer\-ID und das Kennwort, über die Verbindung abgerufen werden, nachdem diese geöffnet wurde.  Wenn Sie `Persist Security Info` hingegen auf `false` oder `no` festlegen, werden die sicherheitsrelevanten Informationen verworfen, sobald die Verbindung mit ihrer Hilfe geöffnet wurde. Auf diese Weise wird dafür gesorgt, dass nicht vertrauenswürdige Quellen nicht auf sicherheitsrelevante Informationen zugreifen können.  
  
## Verschlüsseln von Konfigurationsdateien  
 Sie können die Verbindungszeichenfolgen auch in Konfigurationsdateien speichern. Damit erübrigt sich die Notwendigkeit, die Verbindungszeichenfolgen in den Code Ihrer Anwendung einzubetten.  Konfigurationsdateien sind Standard\-XML\-Dateien, für die .NET Framework einen allgemeinen Satz von Elementen definiert hat.  Verbindungszeichenfolgen in Konfigurationsdateien werden bei Windows\-Anwendungen in der Regel im **\<connectionStrings\>**\-Element in der Datei **app.config** gespeichert. Bei ASP.NET\-Anwendungen erfolgt die Speicherung normalerweise in der Datei **web.config**.  Weitere Informationen zu den Grundlagen von Speichern, Abrufen und Verschlüsseln von Verbindungszeichenfolgen in Konfigurationsdateien finden Sie unter [Verbindungszeichenfolgen und Konfigurationsdateien](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).  
  
## Siehe auch  
 [Sichern von ADO.NET\-Anwendungen](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [Encrypting Configuration Information Using Protected Configuration](../Topic/Encrypting%20Configuration%20Information%20Using%20Protected%20Configuration.md)   
 [Sicherheit in systemeigenem Code und .NET Framework\-Code](http://msdn.microsoft.com/de-de/bd61be84-c143-409a-a75a-44253724f784)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)