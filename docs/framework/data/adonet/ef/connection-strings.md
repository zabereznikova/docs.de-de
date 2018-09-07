---
title: Verbindungszeichenfolgen
ms.date: 03/30/2017
ms.assetid: 78d516bc-c99f-4865-8ff1-d856bc1a01c0
ms.openlocfilehash: 17d91c9b97e370afe3704d2a58f5228e3fec95f1
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44075845"
---
# <a name="connection-strings"></a>Verbindungszeichenfolgen
Eine Verbindungszeichenfolge enthält Initialisierungsinformationen, die als Parameter von einem Datenanbieter an eine Datenquelle übergeben werden. Die Syntax ist abhängig vom Datenanbieter, und die Verbindungszeichenfolge wird beim Versuch analysiert, eine Verbindung herzustellen. Von Entity Framework verwendete Verbindungszeichenfolgen enthalten Informationen zum Herstellen einer Verbindung mit dem zugrunde liegenden ADO.NET-Datenanbieter, der Entity Framework unterstützt. Sie enthalten auch Informationen zu den erforderlichen Modell- und Zuordnungsdateien.  
  
 Der EntityClient-Anbieter verwendet die Verbindungszeichenfolge für den Zugriff auf Modell- und Zuordnungsmetadaten sowie zum Herstellen einer Verbindung mit der Datenquelle. Mithilfe der <xref:System.Data.EntityClient.EntityConnection.ConnectionString%2A>-Eigenschaft der <xref:System.Data.EntityClient.EntityConnection> kann auf die Verbindungszeichenfolge zugegriffen und diese festgelegt werden. Mit der <xref:System.Data.EntityClient.EntityConnectionStringBuilder>-Klasse können Parameter in der Verbindungszeichenfolge programmgesteuert erstellt werden, sie ermöglicht auch den Zugriff auf diese Parameter. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md).  
  
 Die [Entity Data Model-Tools](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527) generieren eine Verbindungszeichenfolge, die in der Konfigurationsdatei der Anwendung gespeichert ist. <xref:System.Data.Objects.ObjectContext> ruft diese Verbindungsinformationen beim Erstellen von Objektabfragen automatisch ab. Auf die <xref:System.Data.EntityClient.EntityConnection>, die von einer <xref:System.Data.Objects.ObjectContext>-Instanz verwendet wird, kann von der <xref:System.Data.Objects.ObjectContext.Connection%2A>-Eigenschaft aus zugegriffen werden. Weitere Informationen finden Sie unter [Verwalten von Verbindungen und Transaktionen](https://msdn.microsoft.com/library/b6659d2a-9a45-4e98-acaa-d7a8029e5b99).  
  
## <a name="connection-string-parameters"></a>Parameter der Verbindungszeichenfolge  
 Das Format einer Verbindungszeichenfolge besteht aus einer durch Semikolons getrennten Liste mit Schlüssel-Wert-Parameterpaaren:  
  
 `keyword1=value; keyword2=value;`  
  
 Ein Gleichheitszeichen (=) verbindet jedes Schlüsselwort mit seinem Wert. Bei den Schlüsselwörtern spielt die Groß- und Kleinschreibung keine Rolle, und Leerzeichen zwischen den Schlüssel-Wert-Paaren werden ignoriert. Je nach Datenquelle ist jedoch bei den Werten auf die Groß-/Kleinschreibung zu achten. Alle Werte, die ein Semikolon, ein einfaches oder ein doppeltes Anführungszeichen enthalten, müssen in doppelte Anführungszeichen eingeschlossen werden. Die folgende Tabelle enthält die gültigen Namen für Schlüsselwortwerte im <xref:System.Data.EntityClient.EntityConnection.ConnectionString%2A>.  
  
|Schlüsselwort|Beschreibung|  
|-------------|-----------------|  
|`Provider`|Erforderlich, wenn das Schlüsselwort `Name` nicht angegeben ist. Der Anbietername, mit dem das <xref:System.Data.Common.DbProviderFactory>-Objekt für den zugrunde liegenden Anbieter abgerufen wird. Dieser Wert ist konstant.<br /><br /> Wenn in einer Entitätsverbindungszeichenfolge nicht das Schlüsselwort `Name` eingefügt wurde, ist für das Schlüsselwort `Provider` ein nicht leerer Wert erforderlich. Dieses Schlüsselwort und das Schlüsselwort `Name` schließen sich gegenseitig aus.|  
|`Provider Connection String`|Dies ist optional. Gibt die anbieterspezifische Verbindungszeichenfolge an, die an die zugrunde liegende Datenquelle übergeben wird. Diese Verbindungszeichenfolge wird mithilfe gültiger Schlüsselwort-Wert-Paare für den Datenanbieter ausgedrückt. Eine ungültige `Provider Connection String` löst bei der Auswertung durch die Datenquelle einen Laufzeitfehler aus.<br /><br /> Dieses Schlüsselwort und das Schlüsselwort `Name` schließen sich gegenseitig aus.<br /><br /> Der Wert der `Provider Connection String` muss durch Anführungszeichen eingeschlossen sein. Im Folgenden finden Sie ein Beispiel dazu:<br /><br /> `Provider Connection String ="Server=serverName; User ID = userID";`<br /><br /> Das folgende Beispiel ist nicht funktionsfähig:<br /><br /> `Provider Connection String =Server=serverName; User ID = userID`|  
|`Metadata`|Erforderlich, wenn das Schlüsselwort `Name` nicht angegeben ist. Eine durch senkrechte Striche getrennte Liste von Verzeichnissen, Dateien und Ressourcenspeicherorten, die nach Metadaten und Mappinginformationen durchsucht werden sollen. Im Folgenden finden Sie ein Beispiel dazu:<br /><br /> `Metadata=`<br /><br /> `c:\model &#124; c:\model\sql\mapping.msl;`<br /><br /> Leerzeichen zu beiden Seiten des senkrechten Strichs werden ignoriert.<br /><br /> Dieses Schlüsselwort und das Schlüsselwort `Name` schließen sich gegenseitig aus.|  
|`Name`|Der Verbindungsname kann von der Anwendung optional in einer Anwendungskonfigurationsdatei angegeben werden, die die erforderlichen Verbindungszeichenfolgen-Werte mit den Schlüsselwort-Wert-Paaren enthält. In diesem Fall können diese nicht direkt in der Verbindungszeichenfolge bereitgestellt werden. Das Schlüsselwort `Name` ist in einer Konfigurationsdatei nicht zulässig.<br /><br /> Wenn das Schlüsselwort `Name` in der Verbindungszeichenfolge nicht eingefügt wurde, ist für das Provider-Schlüsselwort ein nicht leerer Wert erforderlich.<br /><br /> Dieses Schlüsselwort und alle anderen Schlüsselwörter für Verbindungszeichenfolgen schließen sich gegenseitig aus.|  
  
 Folgendes ist ein Beispiel für eine Verbindungszeichenfolge für die [AdventureWorks Sales-Modell](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) in der Anwendungskonfigurationsdatei gespeichert:  
  
  
  
## <a name="model-and-mapping-file-locations"></a>Modell- und Zuordnungsdateispeicherorte  
 Der `Metadata`-Parameter enthält eine Liste mit Speicherorten, an denen der `EntityClient`-Anbieter nach Modell- und Zuordnungsdateien suchen kann. Modell- und Zuordnungsdateien werden häufig im Verzeichnis der ausführbaren Anwendungsdatei bereitgestellt. Diese Dateien können auch in einem anderen Speicherort oder als eingebettete Ressource in der Anwendung bereitgestellt werden.  
  
 Eingebettete Ressourcen werden wie folgt angegeben:  
  
```  
Metadata=res://<assemblyFullName>/<resourceName>.   
```  
  
 Mit den folgenden Optionen kann der Speicherort einer eingebetteten Ressource festgelegt werden:  
  
|Option|Beschreibung|  
|-|-|  
|`assemblyFullName`|Der vollständige Name einer Assembly mit der eingebetteten Ressource. Der Name besteht wie folgt aus dem einfachen Namen, dem Versionsnamen, der unterstützten Kultur und dem öffentlichen Schlüssel:<br /><br /> `ResourceLib, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null`<br /><br /> Ressourcen können in jede Assembly eingebettet werden, auf die von der Anwendung zugegriffen werden kann.<br /><br /> Wenn Sie ein Platzhalterzeichen angeben (\*) für `assemblyFullName`, die Entity Framework-Laufzeit wird nach Ressourcen in den folgenden Speicherorten und in der folgenden Reihenfolge gesucht:<br /><br /> 1.  Die aufrufende Assembly.<br />2.  Die Assemblys, auf die verwiesen wird.<br />3.  Die Assemblys im BIN-Verzeichnis einer Anwendung.<br /><br /> Wenn sich die Dateien nicht in einem dieser Speicherorte befinden, wird eine Ausnahme ausgelöst. **Hinweis:** bei Verwendung von Platzhalterzeichen (*) hat das Entity Framework, allen Assemblys für Ressourcen, mit dem richtigen Namen zu suchen. Wenn anstelle des Platzhalters der Assemblyname eingegeben wird, verbessert sich die Suchleistung.|  
|`resourceName`|Der Name der enthaltenen Ressource, z. B. AdvendtureWorksModel.csdl. Die Metadatendienste suchen nur nach Dateien oder Ressourcen mit folgenden Erweiterungen: CSDL, SSDL oder MSL. Wenn `resourceName` nicht angegeben wurde, werden alle Metadatenressourcen geladen. Die Ressourcen sollten innerhalb einer Assembly eindeutige Namen haben. Wenn in der Assembly mehrere Dateien mit gleichem Namen in verschiedenen Verzeichnissen definiert sind, muss für den `resourceName` die Ordnerstruktur vor dem Ressourcennamen angegeben werden, z. B. Ordnername.Dateiname.csdl.<br /><br /> `resourceName` ist nicht erforderlich, wenn für `assemblyFullName` ein Platzhalter (*) angegeben wird.|  
  
> [!NOTE]
>  Die Leistung kann durch das Einbetten von Ressourcen in die aufrufende Assembly verbessert werden. In nicht webbasierten Szenarios, in denen innerhalb der aufrufenden Assembly keine Verweise auf zugrunde liegende Mapping- und Metadatendateien vorhanden sind, ist dies allerdings nicht möglich.  
  
 In folgendem Beispiel werden alle Modell- und Zuordnungsdateien in die aufrufende Assembly, in Assemblys, auf die verwiesen wird, und in andere Assemblys im BIN-Verzeichnis einer Anwendung geladen.  
  
```  
Metadata=res://*/  
```  
  
 Im folgenden Beispiel werden die Datei model.csdl aus der AdventureWorks-Assembly sowie die Dateien model.ssdl und model.msl aus dem Standardverzeichnis der ausgeführten Anwendung geladen.  
  
```  
Metadata=res://AdventureWorks, 1.0.0.0, neutral, a14f3033def15840/model.csdl|model.ssdl|model.msl  
```  
  
 Im folgenden Beispiel werden die drei festgelegten Ressourcen aus der angegebenen Assembly geladen.  
  
```  
Metadata=res://AdventureWorks, 1.0.0.0, neutral, a14f3033def15840/model.csdl|   
res://AdventureWorks, 1.0.0.0, neutral, a14f3033def15840/model.ssdl|   
res://AdventureWorks, 1.0.0.0, neutral, a14f3033def15840/model.msl  
```  
  
 Im folgenden Beispiel werden alle eingebetteten CSDL-, MSL- und SSDL-Ressourcen aus der Assembly geladen.  
  
```  
Metadata=res://AdventureWorks, 1.0.0.0, neutral, a14f3033def15840/  
```  
  
 Im folgende Beispiel werden alle Ressourcen in den relativen Pfad plus "Datadir\metadata\\" aus dem geladenen Assemblyspeicherort.  
  
```  
Metadata=datadir\metadata\  
```  
  
 Im folgenden Beispiel werden alle Ressourcen aus dem geladenen Assemblyspeicherort in den relativen Dateipfad geladen.  
  
```  
Metadata=.\  
```  
  
## <a name="support-for-the-124datadirectory124-substitution-string-and-the-web-application-root-operator-"></a>Unterstützung für die &#124;"DataDirectory"&#124; -Ersatzzeichenfolge und die Webanwendung Root-Operator (~)  
 `DataDirectory` und der ~-Operator in verwendet werden die <xref:System.Data.EntityClient.EntityConnection.ConnectionString%2A> als Teil der `Metadata` und `Provider Connection String` Schlüsselwörter. Die <xref:System.Data.EntityClient.EntityConnection> leitet den `DataDirectory`- und den ~-Operator an <xref:System.Data.Metadata.Edm.MetadataWorkspace> bzw. den Speicheranbieter weiter.  
  
|Begriff|Beschreibung|  
|----------|-----------------|  
|`&#124;DataDirectory&#124;`|Löst den relativen Pfad in Zuordnungs- und Metadatendateien auf. Dies ist der Wert, der durch die `AppDomain.SetData("DataDirectory", objValue)`-Methode festgelegt wird. Die `DataDirectory` -Ersatzzeichenfolge muss von senkrechten Strichen eingeschlossen sein und dürfen sich keine Leerzeichen zwischen dem Namen und die Pipezeichen. Der `DataDirectory`-Name unterscheidet nicht zwischen Groß- und Kleinschreibung.<br /><br /> Weist auf ein physisches Verzeichnis mit dem Namen "DataDirectory" als Mitglied der Liste der Metadaten übergeben werden, wird eine oder beide Seiten des Namens Leerzeichen hinzugefügt. Beispiel: `Metadata="DataDirectory1 &#124; DataDirectory &#124; DataDirectory2"`. Eine ASP.NET-Anwendung löst &#124;"DataDirectory"&#124; , die "\<Anwendungsstamm > / App_data" Ordner.|  
|~|Löst zum Webanwendungsstamm auf. Wenn sich das Zeichen "~" am Anfang einer Zeichenfolge befindet, wird es stets als Stamm-Operator der Webanwendung (~) interpretiert, auch wenn es möglicherweise ein gültiges lokales Unterverzeichnis darstellt. Wenn auf solch ein lokales Unterverzeichnis verwiesen werden soll, sollte der Benutzer `./~` explizit übergeben.|  
  
 `DataDirectory` und der ~-Operator sollten nur am Anfang eines Pfads festgelegt werden, da sie an anderen Positionen nicht aufgelöst werden. Entity Framework versucht, `~/data` aufzulösen, behandelt `/data/~` jedoch wie einen physischen Pfad.  
  
 Ein Pfad, der mit dem `DataDirectory` oder dem ~-Operator beginnt, kann nicht in einen physischen Pfad außerhalb der Struktur des `DataDirectory` und des ~-Operators aufgelöst werden. Diese Beispielpfade werden aufgelöst: `~`, `~/data`, `~/bin/Model/SqlServer`. Diese Beispielpfade werden nicht aufgelöst: `~/..`, `~/../other`.  
  
 `DataDirectory` und der ~-Operator können wie folgt erweitert werden, um Unterverzeichnisse einzuschließen: `|DataDirectory|\Model`, `~/bin/Model`  
  
 Die Auflösung der `DataDirectory`-Ersatzzeichenfolge und des ~-Operators ist nicht rekursiv. Wenn `DataDirectory` z. B. das `~`-Zeichen enthält, tritt eine Ausnahme auf. Dies verhindert eine unendliche Rekursion.  
  
## <a name="see-also"></a>Siehe auch  
 [Arbeiten mit Datenanbietern](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)  
 [Überlegungen zur Bereitstellung](../../../../../docs/framework/data/adonet/ef/deployment-considerations.md)  
 [Verwalten von Verbindungen und Transaktionen](https://msdn.microsoft.com/library/b6659d2a-9a45-4e98-acaa-d7a8029e5b99)  
 [Verbindungszeichenfolgen](../../../../../docs/framework/data/adonet/connection-strings.md)
