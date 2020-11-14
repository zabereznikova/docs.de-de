---
title: XML Schema Definition-Tool (Xsd.exe)
description: Das XML Serializer Generator-Tool erstellt eine XML-Serialisierungsassembly zur Verbesserung der Startleistung von XmlSerializer für Typen in einer angegebenen Assembly.
ms.date: 03/30/2017
ms.assetid: a6e6e65c-347f-4494-9457-653bf29baac2
ms.openlocfilehash: c8ae3e05f2d775cbc4c44ce27e7474d1fcfc06a3
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "93281757"
---
# <a name="xml-schema-definition-tool-xsdexe"></a>XML Schema Definition-Tool (Xsd.exe)

Das XML Schema Definition-Tool (Xsd.exe) generiert XML-Schema- oder Common Language Runtime-Klassen aus XDR-, XML- und XSD-Dateien oder aus Klassen in einer Laufzeitassembly.

Das XML-Schemadefinitionstool (Xsd.exe) befindet sich in der Regel im folgenden Pfad:\
_C:\\Programme (x86)\\Microsoft SDKs\\Windows\\{Version}\\bin\\NETFX {Version} Tools\\_

## <a name="syntax"></a>Syntax

Führen Sie das Tool über die Befehlszeile aus.

```console
xsd file.xdr [-outputdir:directory][/parameters:file.xml]
xsd file.xml [-outputdir:directory] [/parameters:file.xml]
xsd file.xsd {/classes | /dataset} [/element:element]
             [/enableLinqDataSet] [/language:language]
                          [/namespace:namespace] [-outputdir:directory] [URI:uri]
                          [/parameters:file.xml]
xsd {file.dll | file.exe} [-outputdir:directory] [/type:typename [...]][/parameters:file.xml]
```
  
> [!TIP]
> Damit .NET Framework-Tools einwandfrei funktionieren, müssen die Umgebungsvariablen `Path`, `Include` und `Lib` korrekt festgelegt sein. Führen Sie zum Festlegen dieser Umgebungsvariablen die Datei „SDKVars.bat“ im Verzeichnis „\<SDK>\\\<version>\Bin“ aus. SDKVars.bat muss in jeder Befehlsshell ausgeführt werden.

## <a name="argument"></a>Argument

|Argument|Beschreibung|
|--------------|-----------------|
|*file.extension*|Gibt die zu konvertierende Eingabedatei an. Sie müssen als Erweiterung einen der folgenden Werte angeben: .xdr, .xml, .xsd, .dll oder .exe.<br /><br /> Wenn Sie eine XDR-Schemadatei angeben (Erweiterung .xdr), konvertiert Xsd.exe das XDR-Schema in ein XSD-Schema. Die Ausgabedatei erhält den Namen des XDR-Schemas mit der Erweiterung .xsd.<br /><br /> Wenn Sie eine XML-Datei angeben (Erweiterung .xml), leitet Xsd.exe ein Schema aus den Daten in der Datei ab und erstellt ein XSD-Schema. Die Ausgabedatei erhält den Namen der XML-Datei mit der Erweiterung .xsd.<br /><br /> Wenn Sie eine XML-Schemadatei angeben (Erweiterung .xsd), generiert Xsd.exe Quellcode für Laufzeitobjekte, die dem XML-Schema entsprechen.<br /><br /> Wenn Sie eine Laufzeitassemblydatei angeben (Erweiterung .exe oder .dll), generiert Xsd.exe Schemas für einen oder mehrere Typen in der Assembly. Geben Sie über die `/type`-Option die Typen an, für die Schemas generiert werden sollen. Die Ausgabeschemas erhalten die Bezeichnungen schema0.xsd, schema1.xsd usw. Xsd.exe erstellt nur dann mehrere Schemas, wenn die angegebenen Typen einen Namespace mit dem benutzerdefinierten `XMLRoot`-Attribut angeben.|

## <a name="general-options"></a>Allgemeine Optionen

|Option|Beschreibung|
|------------|-----------------|
|**/h\[elp\]**|Zeigt Befehlssyntax und Optionen für das Tool an.|
|**/o\[utputdir\]:** _Verzeichnis_|Gibt das Verzeichnis für Ausgabedateien an. Dieses Argument kann nur einmal angegeben werden. Der Standardwert ist das aktuelle Verzeichnis.|
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|
|**/p\[arameters\]:** _Datei.xml_|Liest Optionen für verschiedene Operationsmodi aus der angegebenen XML-Datei. Die Kurzform ist `/p:`. Weitere Informationen finden Sie im Abschnitt [Hinweise](#remarks).|

## <a name="xsd-file-options"></a>XSD-Dateioptionen
 Die beiden folgenden Optionen für XSD-Dateien schließen sich gegenseitig aus.

|Option|Beschreibung|
|------------|-----------------|
|**/c\[lasses\]**|Generiert Klassen, die dem angegebenen Schema entsprechen. Verwenden Sie zum Lesen von XML-Daten in das Objekt die <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode.|
|**/d\[ataset\]**|Generiert eine von <xref:System.Data.DataSet> abgeleitete Klasse, die dem angegebenen Schema entspricht. Verwenden Sie zum Lesen von XML-Daten in die abgeleitete Klasse die <xref:System.Data.DataSet.ReadXml%2A?displayProperty=nameWithType>-Methode.|

 Zusätzlich können Sie folgende Optionen für XSD-Dateien angeben.

|Option|Beschreibung|
|------------|-----------------|
|**/e\[lement\]:** _Element_|Gibt das Element im Schema an, für das Code generiert werden soll. In der Standardeinstellung werden für alle Elemente Typen erstellt. Sie können dieses Argument mehrmals angeben.|
|**/enableDataBinding**|Implementiert die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle für alle generierten Typen, um die Datenbindung zu ermöglichen. Die Kurzform ist `/edb`.|
|**/enableLinqDataSet**|(Kurzform: `/eld`) Gibt an, dass das generierte DataSet mit LINQ to DataSet abgefragt werden kann. Diese Option wird verwendet, wenn auch die /dataset-Option angegeben wird. Weitere Informationen finden Sie unter [Übersicht über LINQ to DataSet](../../framework/data/adonet/linq-to-dataset-overview.md) und [Abfragen typisierter DataSets](../../framework/data/adonet/querying-typed-datasets.md). Allgemeine Informationen zur Verwendung von LINQ finden Sie unter [Sprachintegrierte Abfrage (Language-Integrated Query, LINQ) (C#)](../../csharp/programming-guide/concepts/linq/index.md) oder [Language Integrated Query (LINQ) (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/index.md).|
|**/f\[ields\]**|Generiert Felder anstelle von Eigenschaften. Standardmäßig werden Eigenschaften generiert.|
|**/l\[anguage\]:** _Sprache_|Gibt die zu verwendende Programmiersprache an. Wählen Sie `CS` (C#, der Standard), `VB` (Visual Basic), `JS` (JScript) oder `VJS` (Visual J#) aus. Sie können auch einen voll qualifizierten Namen für eine Klasse angeben, die <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementiert.|
|**/n\[amespace\]:** _Namespace_|Gibt den Laufzeitnamespace für die generierten Typen an. Der Standardnamespace ist `Schemas`.|
|**/nologo**|Unterdrückt das Banner.|
|**/order**|Generiert explizite Reihenfolgebezeichner für alle Abschnittsmember.|
|**/o\[ut\]:** _Verzeichnisname_|Gibt das Ausgabeverzeichnis an, in dem die Dateien gespeichert werden sollen. Der Standardwert ist das aktuelle Verzeichnis.|
|**/u\[ri\]:** _URI_|Gibt den URI für die Elemente im Schema an, für die Code generiert werden soll. Dieser URI gilt, soweit vorhanden, für alle Elemente, die mit der `/element`-Option angegeben wurden.|

## <a name="dll-and-exe-file-options"></a>DLL- und EXE-Dateioptionen

|Option|Beschreibung|
|------------|-----------------|
|**/t\[ype\]:** _Typname_|Gibt den Namen des Typs an, für den ein Schema erstellt werden soll. Sie können mehrere Typargumente angeben. Wenn *Typname* keinen Namespace bezeichnet, ordnet „Xsd.exe“ alle Typen in der Assembly dem angegebenen Typ zu. Wenn *Typname* einen Namespace bezeichnet, wird nur der übereinstimmende Typ zugeordnet. Wenn *Typname* auf ein Sternchen (\*) endet, ordnet das Tool alle Typen zu, die mit der Zeichenfolge vor \* beginnen. Wenn Sie die `/type`-Option nicht angeben, generiert Xsd.exe Schemas für alle Typen in der Assembly.|

## <a name="remarks"></a>Hinweise

In der folgenden Tabelle werden die von Xsd.exe ausgeführten Operationen angezeigt.

| | |
|------------|-----------------|
|XDR nach XSD|Generiert ein XML-Schema aus einer XDR-Schemadatei (XML-Data-Reduced). XDR ist ein früheres XML-Schemaformat.|
|XML nach XSD|Generiert ein XML-Schema aus einer XML-Datei.|
|XSD nach DataSet|Generiert <xref:System.Data.DataSet>-Klassen der Common&#160;Language&#160;Runtime aus einer XSD-Schemadatei. Die generierten Klassen stellen ein umfangreiches Objektmodell für reguläre XML-Daten bereit.|
|XSD nach Klassen|Generiert Laufzeitklassen aus einer XSD-Schemadatei. Die generierten Klassen können in Verbindung mit <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType> zum Lesen und Schreiben von XML-Code verwendet werden, der diesem Schema folgt.|
|Klassen nach XSD| Generiert ein XML-Schema aus einem oder mehreren Typen in einer Laufzeitassemblydatei. Das generierte Schema definiert das von der Klasse <xref:System.Xml.Serialization.XmlSerializer> verwendete XML-Format.|

 Mit Xsd.exe können Sie ausschließlich XML-Schemas ändern, die der durch das World Wide Web Consortium (W3C) veröffentlichten XSD-Sprache (XML Schema Definition language) entsprechen. Weitere Informationen zum Vorschlag für die XML-Schemadefinition sowie zum XML-Standard finden Sie unter <https://w3.org>.

## <a name="setting-options-with-an-xml-file"></a>Festlegen von Optionen mit einer XML-Datei

Mithilfe des `/parameters`-Schalters können Sie eine einzelne XML-Datei angeben, durch die verschiedene Optionen festgelegt werden. Welche Optionen Sie festlegen können, richtet sich danach, wie Sie das Tool XSD.exe verwenden. Zu den möglichen Optionen gehören das Generieren von Schemas oder Codedateien sowie das Generieren von Codedateien, die `DataSet`-Funktionen umfassen. So können Sie z.&#160;B. das `<assembly>`-Element auf den Namen einer ausführbaren Datei (.exe) oder Typbibliothek (.dll) festlegen, wenn Sie ein Schema generieren. Dies gilt jedoch nicht für das Generieren von Codedateien. Die folgende XML veranschaulicht die Verwendung des `<generateSchemas>`-Elements mit einer angegebenen ausführbaren Datei:

```xml
<!-- This is in a file named GenerateSchemas.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <assembly>ConsoleApplication1.exe</assembly>
</generateSchemas>
</xsd>
```

Wenn der obige XML-Code in einer Datei mit dem Namen GenerateSchemas.xml enthalten ist, verwenden Sie den Parameter `/parameters`, indem Sie Folgendes in eine Eingabeaufforderung eingeben und die **EINGABETASTE** drücken:

```console
 xsd /p:GenerateSchemas.xml
```

Wenn Sie jedoch ein Schema für einen einzelnen in der Assembly enthaltenen Typ generieren, können Sie folgende XML verwenden:

```xml
<!-- This is in a file named GenerateSchemaFromType.xml. -->
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateSchemas>
   <type>IDItems</type>
</generateSchemas>
</xsd>
```

Um aber den vorangehenden Code zu verwenden, müssen Sie an der Eingabeaufforderung zusätzlich den Namen der Assembly angeben. Geben Sie Folgendes in eine Eingabeaufforderung ein (vorausgesetzt, die XML-Datei hat den Namen GenerateSchemaFromType.xml):

```console
xsd /p:GenerateSchemaFromType.xml ConsoleApplication1.exe
```

Die folgenden Optionen für das `<generateSchemas>`-Element schließen sich gegenseitig aus.

|Element|Beschreibung|
|-------------|-----------------|
|\<assembly>|Gibt eine Assembly an, auf deren Grundlage das Schema generiert werden soll.|
|\<type>|Gibt einen in einer Assembly enthaltenen Typ an, für den ein Schema generiert werden soll.|
|\<xml>|Gibt eine XML-Datei an, für die ein Schema generiert werden soll.|
|\<xdr>|Gibt eine XDR-Datei an, für die ein Schema generiert werden soll.|

Um eine Codedatei zu generieren, verwenden Sie das `<generateClasses>`-Element. Im folgenden Beispiel wird eine Codedatei generiert. Beachten Sie die beiden zusätzlichen Attribute, mit denen Sie Programmiersprache und Namespace der generierten Datei festlegen können.

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
<generateClasses language='VB' namespace='Microsoft.Serialization.Examples'/>
</xsd>
<!-- You must supply an .xsd file when typing in the command line.-->
<!-- For example: xsd /p:genClasses mySchema.xsd -->
```

 Sie können u.&#160;a. folgende Optionen für das `<generateClasses>`-Element festlegen:

|Element|Beschreibung|
|-------------|-----------------|
|\<element>|Gibt ein Element in der XSD-Datei an, für das Code generiert werden soll.|
|\<schemaImporterExtensions>|Gibt einen von der <xref:System.Xml.Serialization.Advanced.SchemaImporterExtension>-Klasse abgeleiteten Typ an.|
|\<schema>|Gibt eine XML-Schemadatei an, für die Code generiert werden soll. Mehrere XML-Schemadateien können mit mehreren \<schema>-Elementen angegeben werden.|

In der folgenden Tabelle sind die Attribute aufgeführt, die zusätzlich mit dem `<generateClasses>`-Element verwendet werden können.

|Attribut|Beschreibung|
|---------------|-----------------|
|language|Gibt die zu verwendende Programmiersprache an. Wählen Sie unter `CS` (C#, dem Standard), `VB` (Visual Basic), `JS` (JScript) oder `VJS` (Visual J#) aus. Sie können auch einen vollqualifizierten Namen für eine Klasse angeben, die <xref:System.CodeDom.Compiler.CodeDomProvider> implementiert.|
|namespace|Gibt den Namespace für den generierten Code an. Der Namespace muss CLR-Standards entsprechen (darf beispielsweise keine Leerzeichen oder umgekehrten Schrägstriche enthalten).|
|Optionen|Einer der folgenden Werte: `none`, `properties` (generiert Eigenschaften anstelle von öffentlichen Feldern), `order` oder `enableDataBinding` (siehe Schalter `/order` und `/enableDataBinding` im vorherigen Abschnitt zu Optionen für XSD-Dateien).|

 Sie können auch steuern, wie `DataSet`-Code generiert wird, indem Sie das `<generateDataSet>`-Element verwenden. In der folgenden XML-Datei wird festgelegt, dass im generierten Code `DataSet`-Strukturen (z. B. die Klasse <xref:System.Data.DataTable>) verwendet werden, um Visual Basic-Code für ein bestimmtes Element zu erstellen. Die generierten DataSet-Strukturen unterstützen LINQ-Abfragen.

 ```xml
 <xsd xmlns='http://microsoft.com/dotnet/tools/xsd/'>
     <generateDataSet language='VB' namespace='Microsoft.Serialization.Examples' enableLinqDataSet='true'>
     </generateDataSet>
 </xsd>
```

Sie können u.&#160;a. folgende Optionen für das `<generateDataSet>`-Element festlegen:

|Element|Beschreibung|
|-------------|-----------------|
|\<schema>|Gibt eine XML-Schemadatei an, für die Code generiert werden soll. Mehrere XML-Schemadateien können mit mehreren \<schema>-Elementen angegeben werden.|

 In der folgenden Tabelle sind die Attribute aufgeführt, die mit dem `<generateDataSet>`-Element verwendet werden können.

|Attribut|Beschreibung|
|---------------|-----------------|
|enableLinqDataSet|Gibt an, dass das generierte DataSet mit LINQ to DataSet abgefragt werden kann. Der Standardwert ist false.|
|language|Gibt die zu verwendende Programmiersprache an. Wählen Sie unter `CS` (C#, dem Standard), `VB` (Visual Basic), `JS` (JScript) oder `VJS` (Visual J#) aus. Sie können auch einen vollqualifizierten Namen für eine Klasse angeben, die <xref:System.CodeDom.Compiler.CodeDomProvider> implementiert.|
|namespace|Gibt den Namespace für den generierten Code an. Der Namespace muss CLR-Standards entsprechen (darf beispielsweise keine Leerzeichen oder umgekehrten Schrägstriche enthalten).|

 Einige Attribute können für das `<xsd>`-Element auf oberster Ebene festgelegt werden. Diese Optionen können mit einem beliebigen untergeordneten Element verwendet werden (`<generateSchemas>`, `<generateClasses>`,`<generateDataSet>` oder ). Im folgenden XML-Code wird Code für ein Element mit dem Namen "IDItems" im Ausgabeverzeichnis mit dem Namen "MyOutputDirectory" generiert.

```xml
<xsd xmlns='http://microsoft.com/dotnet/tools/xsd/' output='MyOutputDirectory'>
<generateClasses>
    <element>IDItems</element>
</generateClasses>
</xsd>
```

In der folgenden Tabelle sind die Attribute aufgeführt, die zusätzlich mit dem `<xsd>`-Element verwendet werden können.

|Attribut|Beschreibung|
|---------------|-----------------|
|Ausgabe|Der Name eines Verzeichnisses, in dem das generierte Schema oder die generierte Codedatei gespeichert wird.|
|nologo|Unterdrückt das Banner. Wird auf `true` oder `false` festgelegt.|
|help|Zeigt Befehlssyntax und Optionen für das Tool an. Wird auf `true` oder `false` festgelegt.|

## <a name="examples"></a>Beispiele
 Der folgende Befehl generiert ein XML-Schema aus `myFile.xdr` und speichert dieses im aktuellen Verzeichnis.

```console
xsd myFile.xdr
```

Der folgende Befehl generiert ein XML-Schema aus `myFile.xml` und speichert dieses im angegebenen Verzeichnis.

```console
xsd myFile.xml /outputdir:myOutputDir
```

Durch den folgenden Befehl wird ein Dataset generiert, das dem angegebenen Schema in der Programmiersprache C# entspricht, und im aktuellen Verzeichnis unter `XSDSchemaFile.cs` gespeichert.

```console
xsd /dataset /language:CS XSDSchemaFile.xsd
```

Der folgende Befehl generiert XML-Schemas für alle Typen in der Assembly `myAssembly.dll` und speichert diese unter `schema0.xsd` im aktuellen Verzeichnis.

```console
xsd myAssembly.dll
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataSet>
- <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
- [Extras](../../framework/tools/index.md)
- [Eingabeaufforderungen](../../framework/tools/developer-command-prompt-for-vs.md)
- [Übersicht über LINQ to DataSet](../../framework/data/adonet/linq-to-dataset-overview.md)
- [Abfragen von typisierten DataSets](../../framework/data/adonet/querying-typed-datasets.md)
- [Sprachintegrierte Abfrage (Language-Integrated Query, LINQ) (C#)](../../csharp/programming-guide/concepts/linq/index.md)
- [Language Integrated Query (LINQ) (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/index.md)
