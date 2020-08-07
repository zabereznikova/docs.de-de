---
title: SqlMetal.exe (Tool zur Codegenerierung)
description: Informieren Sie sich über „SqlMetal.exe“, das Tool zur Codegenerierung. Verwenden Sie das Tool, um Code und Zuordnungen für die LINQ to SQL-Komponente von .NET zu generieren.
ms.date: 03/30/2017
helpviewer_keywords:
- SQLMetal [LINQ to SQL]
- code generation tool
- SQLMetal.exe
- LINQ to SQL, serialization
- LINQ to SQL, DBML files
- LINQ to SQL, SQLMetal
ms.assetid: 819e5a96-7646-4fdb-b14b-fe31221b0614
ms.openlocfilehash: 84cad85a7a9fc4b420b57543b7f258607be4ab52
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517047"
---
# <a name="sqlmetalexe-code-generation-tool"></a>SqlMetal.exe (Tool zur Codegenerierung)
Das SqlMetal-Befehlszeilentool generiert Code und Zuordnungen für die [!INCLUDE[vbtecdlinq](../../../includes/vbtecdlinq-md.md)]-Komponente von .NET Framework. Durch Anwenden der später in diesem Thema behandelten Optionen können Sie SqlMetal anweisen, mehrere verschiedene Aktionen wie etwa die folgenden auszuführen:  
  
- Generieren von Quellcode und Zuordnungsattributen oder einer Zuordnungsdatei von einer Datenbank aus  
  
- Generieren einer DBML-Datei (Intermediate Database Markup Language) zum Anpassen von einer Datenbank aus  
  
- Generieren von Code und Zuordnungsattributen oder einer Zuordnungsdatei von einer DBML-Datei aus  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Standardmäßig befindet sich die Datei unter " `drive`:\Programme\Microsoft SDKs\Windows\v`n.nn`\bin". Wenn Sie Visual Studio nicht installieren, können Sie die SQLMetal-Datei auch über einen Download des [Windows SDK](https://go.microsoft.com/fwlink/?LinkId=142225)erhalten.  
  
> [!NOTE]
> Entwickler, die Visual Studio verwenden, können auch den objektrelationalen Designer verwenden, um Entitätsklassen zu generieren. Die Befehlszeilenmethode ist für umfangreiche Datenbanken gut skalierbar. Da SqlMetal ein Befehlszeilentool ist, können Sie es in einem Buildprozess verwenden.  
  
 Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen. Weitere Informationen finden Sie unter [Command Prompts (Eingabeaufforderung)](developer-command-prompt-for-vs.md). Geben Sie bei er Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```console  
sqlmetal [options] [<input file>]  
```  
  
## <a name="options"></a>Tastatur  
 Geben Sie zum Anzeigen der aktuellsten Optionsliste `sqlmetal /?` in einer Eingabeaufforderung am installierten Speicherort ein.  
  
 **Verbindungsoptionen**  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/server:** *\<name>*|Gibt den Datenbank-Servernamen an.|  
|**/database:** *\<name>*|Gibt den Datenbankkatalog auf dem Server an.|  
|**/user:** *\<name>*|Gibt die Benutzer-ID für die Anmeldung an. Standardwert: Verwenden der Windows-Authentifizierung.|  
|**/password:** *\<password>*|Gibt das Anmeldekennwort an. Standardwert: Verwenden der Windows-Authentifizierung.|  
|**/conn:** *\<connection string>*|Gibt die Verbindungszeichenfolge für Datenbanken an. Kann nicht mit den Optionen **/server**, **/database**, **/user**oder **/password** verwendet werden.<br /><br /> Die Verbindungszeichenfolge darf den Dateinamen nicht enthalten. Fügen Sie stattdessen den Dateinamen in der Befehlszeile als Eingabedatei hinzu. In der folgenden Zeile ist beispielsweise „c:\northwnd.mdf“ als Eingabedatei angegeben: **sqlmetal /code:"c:\northwind.cs" /language:csharp "c:\northwnd.mdf"** .|  
|**/timeout:** *\<seconds>*|Gibt den Timeoutwert an, wenn SqlMetal auf die Datenbank zugreift. Standardwert: 0 (d. h. kein Zeitlimit).|  
  
 **Extraktionsoptionen**  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/views**|Extrahiert Datenbankansichten.|  
|**/functions**|Extrahiert Datenbankfunktionen.|  
|**/sprocs**|Extrahiert gespeicherte Prozeduren.|  
  
 **Ausgabeoptionen**  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/dbml** *[:file]*|Sendet die Ausgabe als DBML-Datei. Kann nicht zusammen mit der Option **/map** verwendet werden.|  
|**/code** *[:file]*|Sendet die Ausgabe als Quellcode. Kann nicht zusammen mit der Option **/dbml** verwendet werden.|  
|**/map** *[:file]*|Generiert anstelle von Attributen eine XML-Zuordnungsdatei. Kann nicht zusammen mit der Option **/dbml** verwendet werden.|  
  
 **Verschiedenes**  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**/language:** *\<language>*|Gibt die Quellcodesprache an.<br /><br /> Gültige *\<language>* : vb, csharp.<br /><br /> Standardwert: von der Erweiterung des Namens der Codedatei abgeleitet.|  
|**/namespace:** *\<name>*|Gibt den Namespace des generierten Codes an. Standardwert: kein Namespace.|  
|**/context:** *\<type>*|Gibt Namen der Datenkontextklasse an. Standardwert: vom Datenbanknamen abgeleitet.|  
|**/entitybase:** *\<type>*|Gibt die Basisklasse der Entitätsklassen im generierten Code an. Standardwert: Entitäten verfügen über keine Basisklasse.|  
|**/pluralize**|Klassen- und Membernamen werden automatisch in Plural- oder Singularform verwendet.<br /><br /> Diese Option ist nur in der englischen Version (US-Version) verfügbar.|  
|**/serialization:** *\<option>*|Generiert serialisierbare Klassen.<br /><br /> Gültige *\<option>* : None, Unidirectional. Standardwert: Keine<br /><br /> Weitere Informationen finden Sie unter [Serialization (Serialisierung)](../data/adonet/sql/linq/serialization.md).|  
  
 **Eingabedatei**  
  
|Option|BESCHREIBUNG|  
|------------|-----------------|  
|**\<input file>**|Gibt eine SQL Server Express-Datei (.mdf), eine SQL Server Compact 3.5-Datei (.sdf) oder eine Zwischendatei (.dbml) an.|  
  
## <a name="remarks"></a>Hinweise  
 Die SqlMetal-Funktionalität umfasst eigentlich zwei Schritte:  
  
- Extrahieren der Datenbank-Metadaten in eine DBML-Datei  
  
- Generieren einer Codeausgabedatei  
  
     Durch Verwenden der entsprechenden Befehlszeilenoptionen können Sie Visual Basic- oder C#-Quellcode bzw. eine XML-Zuordnungsdatei erstellen.  
  
 Um die Metadaten aus einer MDF-Datei zu extrahieren, müssen Sie den Namen der MDF-Datei nach allen anderen Optionen eingeben.  
  
 Wenn **/Server** nicht angegeben ist, wird **localhost/sqlexpress** angenommen.  
  
 Microsoft SQL Server 2005 löst eine Ausnahme aus, wenn mindestens eine der folgenden Bedingungen erfüllt ist:  
  
- SqlMetal versucht, eine gespeicherte Prozedur zu extrahieren, die sich selbst aufruft.  
  
- Die Schachtelungsebene einer gespeicherten Prozedur, Funktion, oder Ansicht übersteigt 32.  
  
     SqlMetal fängt diese Ausnahme ab und gibt sie als Warnung aus.  
  
 Um einen Namen für eine Eingabedatei anzugeben, fügen Sie den Namen der Befehlszeile als Eingabedatei hinzu. Die Angabe des Dateinamens in der Verbindungszeichenfolge (mithilfe der Option **/conn** ) wird nicht unterstützt.  
  
## <a name="examples"></a>Beispiele  
 Generiert eine DBML-Datei, die extrahierte SQL-Metadaten umfasst:  
  
 **sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml**  
  
 Generiert mithilfe von SQL Server Express eine DBML-Datei, die extrahierte SQL-Metadaten aus einer MDF-Datei umfasst:  
  
 **sqlmetal /dbml:mymeta.dbml mydbfile.mdf**  
  
 Generiert aus SQL Server Express eine DBML-Datei, die extrahierte SQL-Metadaten umfasst:  
  
 **sqlmetal /server:.\sqlexpress /dbml:mymeta.dbml /database:northwind**  
  
 Generiert Quellcode aus einer DBML-Metadatendatei:  
  
 **sqlmetal /namespace:nwind /code:nwind.cs /language:csharp mymetal.dbml**  
  
 Generiert Quellcode direkt aus SQL-Metadaten:  
  
 **sqlmetal /server:myserver /database:northwind /namespace:nwind /code:nwind.cs /language:csharp**  
  
> [!NOTE]
> Wenn Sie die Option **/pluralize** mit der Northwind-Beispieldatenbank verwenden, stellen Sie folgendes Verhalten fest. Wenn SqlMetal Zeilentypnamen für Tabellen erstellt, wird für Tabellennamen die Singularform verwendet. Wenn <xref:System.Data.Linq.DataContext> -Eigenschaften für Tabellen erstellt werden, wird für Tabellennamen die Pluralform verwendet. Zufällig treten die Tabellen in der Northwind-Beispieldatenbank bereits in Pluralform auf. Deshalb ist nicht erkennbar, dass dieser Schritt funktioniert. Obwohl es üblich ist, Datenbanktabellen im Singular zu benennen, ist es in .NET auch verbreitet, Auflistungen in Pluralform zu benennen.  
  
## <a name="see-also"></a>Siehe auch

- [How to: (Vorgehensweise: Generieren des Objektmodells in Visual Basic oder C#)](../data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
- [Codegenerierung in LINQ to SQL](../data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [External Mapping (Externe Zuordnung)](../data/adonet/sql/linq/external-mapping.md)
