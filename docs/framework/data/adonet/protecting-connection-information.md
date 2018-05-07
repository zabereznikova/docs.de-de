---
title: Schützen von Verbindungsinformationen
ms.date: 03/30/2017
ms.assetid: 1471f580-bcd4-4046-bdaf-d2541ecda2f4
ms.openlocfilehash: 4cf503af6f57eefb0990a8e7e728ea5c1474bfa7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="protecting-connection-information"></a>Schützen von Verbindungsinformationen
Eines der wichtigsten Ziele beim Sichern einer Anwendung besteht darin, den Zugriff auf die Datenquelle zu schützen. Eine Verbindungszeichenfolge stellt ein potenzielles Sicherheitsrisiko dar, wenn sie nicht gesichert wird. Das Speichern von Verbindungsinformationen als Klartext oder das Aufbewahren dieser Informationen im Arbeitsspeicher gefährdet Ihr gesamtes System. In Ihrem Quellcode eingebettete Verbindungszeichenfolgen können gelesen werden, mithilfe der [Ildasm.exe (IL-Disassembler)](../../../../docs/framework/tools/ildasm-exe-il-disassembler.md) um Microsoft intermediate Language (MSIL) in einer kompilierten Assembly anzuzeigen.  
  
 Welche Sicherheitsrisiken sich im Zusammenhang mit Verbindungszeichenfolgen ergeben, hängt von der Art der verwendeten Authentifizierung, der Art und Weise, wie die Verbindungszeichenfolgen im Arbeitsspeicher und auf der Festplatte aufbewahrt werden, und den Verfahren ab, mit denen die Verbindungszeichenfolgen zur Laufzeit konstruiert werden.  
  
## <a name="use-windows-authentication"></a>Verwenden Sie die Windows-Authentifizierung.  
 Damit der Zugriff auf die Datenquelle geschützt bleibt, müssen Sie Verbindungsinformationen wie Benutzer-ID, Kennwort und den Namen der Datenquelle sichern. Um zu vermeiden, dass Benutzerinformationen verfügbar gemacht, es wird empfohlen, Windows-Authentifizierung (auch bezeichnet als *integrierte Sicherheit von*) möglich. Die Windows-Authentifizierung wird in einer Verbindungszeichenfolge mit dem Schlüsselwort `Integrated Security` oder `Trusted_Connection` angegeben, sodass weder eine Benutzer-ID noch ein Kennwort verwendet werden muss. Bei Verwendung der Windows-Authentifizierung werden die Benutzer von Windows authentifiziert, und der Zugriff auf Server- und Datenbankressourcen wird durch die Erteilung von Berechtigungen für Windows-Benutzer und -Gruppen gesteuert.  
  
 Dort, wo die Windows-Authentifizierung nicht verwendet werden kann, müssen Sie besondere Vorsicht walten lassen, da die Verbindungszeichenfolge Benutzeranmeldeinformationen enthält, die offen zugänglich sind. In ASP.NET-Anwendungen können Sie ein Windows-Konto als feste Identität konfigurieren, die dann für Verbindungen mit Datenbanken und anderen Netzwerkressourcen verwendet wird. Aktivieren Sie den Identitätswechsel im Identitätselement in der **"Web.config"** Datei, und geben Sie einen Benutzernamen und Kennwort.  
  
```xml  
<identity impersonate="true"   
        userName="MyDomain\UserAccount"   
        password="*****" />  
```  
  
 Das Konto mit der festen Identität sollte nur über die nötigsten Berechtigungen für die Datenbank verfügen. Außerdem sollten Sie die Konfigurationsdatei verschlüsseln, sodass der Benutzername und das Kennwort nicht als Klartext verfügbar gemacht werden.  
  
## <a name="do-not-use-universal-data-link-udl-files"></a>Verwenden Sie keine UDL-Dateien (Universal Data Link)  
 Vermeiden Sie, Verbindungszeichenfolgen für eine <xref:System.Data.OleDb.OleDbConnection> in einer UDL-Datei (Universal Data Link, universelle Datenverknüpfung) zu speichern. Informationen in UDLs werden in Klartext gespeichert und können nicht verschlüsselt werden. Bei einer UDL-Datei handelt es sich um eine externe dateibasierte Ressource der Anwendung, die mit .NET Framework nicht gesichert oder verschlüsselt werden kann.  
  
## <a name="avoid-injection-attacks-with-connection-string-builders"></a>Vermeiden von Einfügeangriffen mit Verbindungszeichenfolgen-Generatoren  
 Zu einem Angriff durch Einschleusen von Verbindungszeichenfolgen kann es kommen, wenn die dynamische Zeichenfolgenverkettung verwendet wird, um auf Benutzereingabe basierende Verbindungszeichenfolgen zu konstruieren. Wenn die Benutzereingabe nicht validiert wird und schädlicher Text (oder schädliche Zeichen) nicht maskiert wird, kann ein Angreifer möglicherweise auf sicherheitsrelevante Daten oder andere Ressourcen auf dem Server zugreifen. Zur Vermeidung dieses Problems enthält ADO.NET 2.0 neue Verbindungszeichenfolgen-Generatorklassen, mit deren Hilfe die Verbindungszeichenfolgensyntax validiert und sichergestellt werden kann, dass keine zusätzlichen Parameter eingeschleust werden. Weitere Informationen finden Sie unter [Verbindungszeichenfolgen-Generatoren](../../../../docs/framework/data/adonet/connection-string-builders.md).  
  
## <a name="use-persist-security-infofalse"></a>Verwenden von "Persist Security Info=False"  
 Die Standardeinstellung für `Persist Security Info` ist false. Wir empfehlen, diesen Standardwert in allen Verbindungszeichenfolgen beizubehalten. Wenn Sie `Persist Security Info` auf `true` oder `yes` festlegen, können sicherheitsrelevante Informationen, wie die Benutzer-ID und das Kennwort, über die Verbindung abgerufen werden, nachdem diese geöffnet wurde. Wenn Sie `Persist Security Info` hingegen auf `false` oder `no` festlegen, werden die sicherheitsrelevanten Informationen verworfen, sobald die Verbindung mit ihrer Hilfe geöffnet wurde. Auf diese Weise wird dafür gesorgt, dass nicht vertrauenswürdige Quellen nicht auf sicherheitsrelevante Informationen zugreifen können.  
  
## <a name="encrypt-configuration-files"></a>Verschlüsseln von Konfigurationsdateien  
 Sie können die Verbindungszeichenfolgen auch in Konfigurationsdateien speichern. Damit erübrigt sich die Notwendigkeit, die Verbindungszeichenfolgen in den Code Ihrer Anwendung einzubetten. Konfigurationsdateien sind Standard-XML-Dateien, für die .NET Framework einen allgemeinen Satz von Elementen definiert hat. Verbindungszeichenfolgen in Konfigurationsdateien befinden sich in der Regel innerhalb der  **\<ConnectionStrings >** Element in der **"App.config"** für eine Windows-Anwendung oder die  **"Web.config"** Datei für eine ASP.NET-Anwendung. Weitere Informationen zu den Grundlagen zum Speichern, abrufen und Verschlüsseln von Verbindungszeichenfolgen aus Konfigurationsdateien finden Sie unter [Verbindungszeichenfolgen und Konfigurationsdateien](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Verschlüsseln von Konfigurationsinformationen mithilfe der geschützten Konfiguration](http://msdn.microsoft.com/library/51cdfe5b-9d82-458c-94ff-c551c4f38ed1)  
 [PAVE Security in Native and .NET Framework Code (PAVE-Sicherheit in nativem und .NET Framework-Code)](http://msdn.microsoft.com/library/bd61be84-c143-409a-a75a-44253724f784)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
