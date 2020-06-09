---
title: Importieren von Schemas zum Generieren von Klassen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractImporter class
ms.assetid: b9170583-8c34-43bd-97bb-6c0c8dddeee0
ms.openlocfilehash: 01f5162727a213fa5dcdf8a70e4e8e4c3627f086
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596902"
---
# <a name="importing-schema-to-generate-classes"></a>Importieren von Schemas zum Generieren von Klassen
Verwenden Sie die-Klasse, um Klassen aus Schemas zu generieren, die mit Windows Communication Foundation (WCF) verwendet werden können <xref:System.Runtime.Serialization.XsdDataContractImporter> . In diesem Thema werden der Prozess und die Variationen beschrieben.  
  
## <a name="the-import-process"></a>Der Importprozess
 Der Schemaimportprozess beginnt mit <xref:System.Xml.Schema.XmlSchemaSet> und erzeugt ein <xref:System.CodeDom.CodeCompileUnit>-Element.  
  
 Der `XmlSchemaSet` ist ein Teil des Schema Objektmodells (SOM) des .NET Framework, das einen Satz von XSD-Schema Dokumenten (XML Schema Definition Language) darstellt. Um ein `XmlSchemaSet`-Objekt aus einer Gruppe von XSD-Dokumenten zu erstellen, deserialisieren Sie die einzelnen Dokumente in ein <xref:System.Xml.Schema.XmlSchema>-Objekt (mithilfe von <xref:System.Xml.Serialization.XmlSerializer>) und fügen diese Objekte einem neuen `XmlSchemaSet`-Element hinzu.  
  
 Der `CodeCompileUnit` ist Teil des .NET Framework Code Document Object Model (CodeDom), der .NET Framework Code auf abstrakte Weise darstellt. Um den eigentlichen Code aus einer `CodeCompileUnit` zu generieren, verwenden Sie eine Unterklasse der <xref:System.CodeDom.Compiler.CodeDomProvider>-Klasse, zum Beispiel die <xref:Microsoft.CSharp.CSharpCodeProvider>- oder <xref:Microsoft.VisualBasic.VBCodeProvider>-Klasse.  
  
### <a name="to-import-a-schema"></a>So importieren Sie ein Schema  
  
1. Erstellen Sie eine Instanz der <xref:System.Runtime.Serialization.XsdDataContractImporter>.  
  
2. Optional. Übergeben Sie im Konstruktor eine `CodeCompileUnit`. Die während des Schemaimports generierten Typen werden dieser `CodeCompileUnit`-Instanz hinzugefügt. Es wird keine leere `CodeCompileUnit` verwendet.  
  
3. Optional. Rufen Sie eine der <xref:System.Runtime.Serialization.XsdDataContractImporter.CanImport%2A> -Methoden auf. Die Methode bestimmt, ob es sich beim jeweiligen Schema um ein gültiges Datenvertragsschema handelt und ob es importiert werden kann. Die `CanImport`-Methode verfügt über die gleichen Überladungen wie `Import` (der nächste Schritt).  
  
4. Rufen Sie eine der überladenen `Import`-Methoden auf, zum Beispiel die <xref:System.Runtime.Serialization.XsdDataContractImporter.Import%28System.Xml.Schema.XmlSchemaSet%29>-Methode.  
  
     Bei der einfachsten Überladung wird ein `XmlSchemaSet` verwendet, und es werden alle Typen importiert, die im Schemasatz enthalten sind, einschließlich anonyme Typen. Bei anderen Überladungen können Sie den XSD-Typ oder eine Liste der Typen angeben, die importiert werden sollen (in Form eines <xref:System.Xml.XmlQualifiedName>-Objekts oder einer Auflistung mit `XmlQualifiedName`-Objekten). In diesem Fall werden nur die angegebenen Typen importiert. Eine Überladung verwendet ein <xref:System.Xml.Schema.XmlSchemaElement>, das ein bestimmtes Element aus dem `XmlSchemaSet` importiert, einschließlich des dazugehörigen Typs (anonym oder nicht anonym). Diese Überladung gibt einen `XmlQualifiedName` zurück, der für den Datenvertragsnamen des Typs steht, der für dieses Element generiert wurde.  
  
     Mehrere Aufrufe der `Import`-Methode führen dazu, dass mehrere Elemente derselben `CodeCompileUnit` hinzugefügt werden. Ein Typ wird nicht für den `CodeCompileUnit` generiert, wenn er darin bereits vorhanden ist. Rufen Sie `Import` für einen `XsdDataContractImporter` mehrfach auf, anstatt mehrere `XsdDataContractImporter`-Objekte zu verwenden. Dies ist die empfohlene Möglichkeit, um die Generierung von doppelten Typen zu vermeiden.  
  
    > [!NOTE]
    > Wenn beim Importieren ein Fehler auftritt, befindet sich die `CodeCompileUnit` in einem unvorhersehbaren Zustand. Wenn Sie eine `CodeCompileUnit` verwenden, die aus einem fehlgeschlagenen Import stammt, kann Sie dies ggf. anfällig für Sicherheitslücken machen.  
  
5. Greifen Sie auf die `CodeCompileUnit` mithilfe der <xref:System.Runtime.Serialization.XsdDataContractImporter.CodeCompileUnit%2A> -Eigenschaft zu.  
  
### <a name="import-options-customizing-the-generated-types"></a>Importoptionen: Anpassen der generierten Typen  
 Sie können die <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A>-Eigenschaft von <xref:System.Runtime.Serialization.XsdDataContractImporter> auf eine Instanz der <xref:System.Runtime.Serialization.ImportOptions>-Klasse festlegen, um verschiedene Aspekte des Importprozesses zu steuern. Verschiedene Optionen wirken sich direkt auf die generierten Typen aus.  
  
#### <a name="controlling-the-access-level-generateinternal-or-the-internal-switch"></a>Steuern der Zugriffsebene (GenerateInternal oder der Schalter "/internal")  
 Dies entspricht dem Schalter **Schalter/Internal** für das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
 Normalerweise werden öffentliche Typen aus Schemas generiert, indem private Felder und passende Eigenschaften öffentlicher Datenmember verwendet werden. Wenn Sie stattdessen interne Typen generieren möchten, legen Sie die <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A>-Eigenschaft auf `true` fest.  
  
 Das folgende Beispiel zeigt ein Schema, das in eine interne Klasse umgewandelt wird, wenn die <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A>-Eigenschaft auf `true.` festgelegt ist.  
  
 [!code-csharp[c_SchemaImportExport#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#2)]
 [!code-vb[c_SchemaImportExport#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#2)]  
  
#### <a name="controlling-namespaces-namespaces-or-the-namespace-switch"></a>Steuern von Namespaces (Namespaces oder der Schalter "/namespace")  
 Dies entspricht dem Schalter **/Namespace** für das `Svcutil.exe` Tool.  
  
 Normalerweise werden Typen, die aus dem Schema generiert werden, in .NET Framework Namespaces generiert, wobei jeder XSD-Namespace einem bestimmten .NET Framework Namespace entsprechend einer in der [Daten Vertrags Schema Referenz](data-contract-schema-reference.md)beschriebenen Zuordnung entspricht. Sie können diese Zuordnung mithilfe der <xref:System.Runtime.Serialization.ImportOptions.Namespaces%2A>-Eigenschaft eines <xref:System.Collections.Generic.Dictionary%602> anpassen. Wenn ein bestimmter XSD-Namespace im Wörterbuch gefunden wird, wird auch der übereinstimmende .NET Framework Namespace aus Ihrem Wörterbuch entnommen.  
  
 Betrachten Sie zum Beispiel das folgende Schema:  
  
 [!code-xml[c_SchemaImportExport#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#10)]  
  
 Im folgenden Beispiel wird die- `Namespaces` Eigenschaft verwendet, um den- `http://schemas.contoso.com/carSchema` Namespace "" "" "".  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
#### <a name="adding-the-serializableattribute-generateserializable-or-the-serializable-switch"></a>Hinzufügen von SerializableAttribute (GenerateSerializable oder der Schalter "/serializable")  
 Dies entspricht dem Schalter **/Serializable** für das `Svcutil.exe` Tool.  
  
 Manchmal ist es wichtig, dass die aus dem Schema generierten Typen mit .NET Framework Laufzeitserialisierungsmodulen verwendet werden können (z <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> . b. die-Klasse und die- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Klasse). Dies ist nützlich, wenn Sie Typen für .NET Framework Remoting verwenden. Um dies zu aktivieren, müssen Sie das <xref:System.SerializableAttribute>-Attribut zusätzlich zum normalen <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf die generierten Typen anwenden. Das Attribut wird automatisch generiert, wenn die Importoption `GenerateSerializable` auf `true` festgelegt ist.  
  
 Das folgende Beispiel zeigt die `Vehicle`-Klasse, bei deren Generierung die Importoption `GenerateSerializable` auf `true` festgelegt ist.  
  
 [!code-csharp[c_SchemaImportExport#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#4)]
 [!code-vb[c_SchemaImportExport#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#4)]  
  
#### <a name="adding-data-binding-support-enabledatabinding-or-the-enabledatabinding-switch"></a>Hinzufügen von Datenbindungsunterstützung (EnableDataBinding oder der Schalter „/enableDataBinding“)  
 Dies entspricht dem Schalter **Schalter/enableDataBinding im** für das Tool Svcutil. exe.  
  
 In einigen Fällen kann es ratsam sein, die aus dem Schema generierten Typen an Komponenten der grafischen Benutzeroberfläche zu binden, damit die Aktualisierungen der Instanzen dieser Typen automatisch auf der Benutzeroberfläche widergespiegelt werden. Der `XsdDataContractImporter` kann Typen generieren, die die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle so implementieren, dass alle Änderungen von Eigenschaften ein Ereignis auslösen. Wenn Sie Typen für die Verwendung mit einer Client-UI-Programmierumgebung erstellen, die diese Schnittstelle unterstützt (z. b. Windows Presentation Foundation (WPF)), legen Sie die- <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> Eigenschaft auf fest, `true` um diese Funktion zu aktivieren  
  
 Das folgende Beispiel zeigt die `Vehicle`-Klasse, bei deren Generierung <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> auf `true` festgelegt ist.  
  
 [!code-csharp[C_SchemaImportExport#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#5)]
 [!code-vb[C_SchemaImportExport#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#5)]  
  
### <a name="import-options-choosing-collection-types"></a>Importoptionen: Wählen von Auflistungstypen  
 Zwei spezielle XML-Muster stellen Auflistungen von Elementen dar: Listen mit Elementen und Zuordnungen zwischen einem Element und einem anderen. Unten ist ein Beispiel für eine Liste mit Zeichenfolgen angegeben.  
  
 [!code-xml[C_SchemaImportExport#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#11)]  
  
 Das folgende Beispiel zeigt eine Zuordnung zwischen einer Zeichenfolge und einer Ganzzahl (`city name` und `population`).  
  
 [!code-xml[C_SchemaImportExport#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#12)]  
  
> [!NOTE]
> Jede Zuordnung kann auch als Liste angesehen werden. Sie können die oben angegebene Zuordnung zum Beispiel als Liste mit komplexen `city`-Objekten ansehen, die zwei Felder aufweisen (ein Zeichenfolgenfeld und ein Ganzzahlfeld). Beide Muster verfügen im XSD-Schema über eine Darstellung. Es gibt keine Möglichkeit, eine Liste und eine Zuordnung zu unterscheiden, sodass solche Muster immer als Listen behandelt werden, es sei denn, eine spezielle Anmerkung für WCF ist im Schema vorhanden. Die Anmerkung gibt an, dass ein bestimmtes Muster eine Zuordnung darstellt. Weitere Informationen finden Sie unter [Daten Vertrags Schema-Referenz](data-contract-schema-reference.md).  
  
 Normalerweise wird eine Liste als Sammlungs Datenvertrag importiert, der von einer generischen Liste oder als .NET Framework Array abgeleitet wird, je nachdem, ob das Schema dem Standard Benennungs Muster für Auflistungen folgt. Dies wird in den [Sammlungs Typen in Daten Verträgen](collection-types-in-data-contracts.md)ausführlicher beschrieben. Zuordnungen werden normalerweise entweder als <xref:System.Collections.Generic.Dictionary%602> oder als Auflistungsdatenvertrag importiert, der vom Wörterbuchobjekt abgeleitet ist. Betrachten Sie zum Beispiel das folgende Schema:  
  
 [!code-xml[c_SchemaImportExport#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#13)]  
  
 Der Import wird hierbei wie folgt durchgeführt (aus Gründen der besseren Lesbarkeit werden anstelle von Eigenschaften Felder angezeigt).  
  
 [!code-csharp[c_SchemaImportExport#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#6)]
 [!code-vb[c_SchemaImportExport#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#6)]  
  
 Es ist möglich, die Auflistungstypen anzupassen, die für Schemamuster dieser Art generiert werden. Es kann beispielsweise sein, dass Sie Auflistungen generieren, die von <xref:System.ComponentModel.BindingList%601> abgeleitet sind, anstatt von der <xref:System.Collections.Generic.List%601>-Klasse, um den Typ an ein Listenfeld zu binden und automatisch aktualisieren zu lassen, wenn sich der Inhalt der Auflistung ändert. Legen Sie dazu die <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A>-Eigenschaft der <xref:System.Runtime.Serialization.ImportOptions>-Klasse auf eine Liste mit zu verwendenden Auflistungstypen (im Weiteren als referenzierte Typen bezeichnet) fest. Beim Importieren von Auflistungen wird diese Liste mit Verweisen zu Auflistungstypen durchsucht und die Auflistung mit der höchsten Übereinstimmung verwendet, falls vorhanden. Es ergeben sich bei Zuordnungen nur für Typen Übereinstimmungen, die entweder die generische oder die nicht generische <xref:System.Collections.IDictionary>-Schnittstelle implementieren, während sich bei Listen für alle unterstützten Auflistungstypen Übereinstimmungen ergeben können.  
  
 Wenn die <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A>-Eigenschaft zum Beispiel auf eine <xref:System.ComponentModel.BindingList%601> festgelegt ist, wird der `people`-Typ aus dem vorherigen Beispiel wie folgt generiert.  
  
 [!code-csharp[C_SchemaImportExport#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#7)]
 [!code-vb[C_SchemaImportExport#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#7)]  
  
 Ein geschlossener generischer Typ wird als beste Übereinstimmung betrachtet. Wenn beispielsweise die Typen `BindingList(Of Integer)` und <xref:System.Collections.ArrayList> an die Auflistung der referenzierten Typen übergeben werden, werden alle Listen mit Ganzzahlen, die im Schema enthalten sind, als `BindingList(Of Integer)` importiert. Alle anderen Listen, zum Beispiel `List(Of String)`, werden als `ArrayList` importiert.  
  
 Wenn ein Typ, der die generische `IDictionary`-Schnittstelle implementiert, der Auflistung der referenzierten Typen hinzugefügt wird, müssen ihre Typparameter entweder vollständig offen oder vollständig geschlossen sein.  
  
 Duplikate sind nicht zulässig. Zum Beispiel können Sie den referenzierten Typen nicht sowohl eine `List(Of Integer)` als auch eine `Collection(Of Integer)` hinzufügen. In diesem Fall wäre es unmöglich zu bestimmen, welches Element verwendet werden soll, wenn im Schema eine Liste mit Ganzzahlen gefunden wird. Duplikate werden nur erkannt, wenn es einen Typ im Schema gibt, der das Duplikatproblem offenlegt. Wenn das importierte Schema zum Beispiel keine Listen mit Ganzzahlen enthält, ist es zulässig, sowohl die `List(Of Integer)` als auch die `Collection(Of Integer)` in der Auflistung mit den referenzierten Typen zu verwenden, aber beide haben keine Auswirkung.  
  
 Der Mechanismus mit den referenzierten Auflistungstypen funktioniert ebenso gut für Auflistungen mit komplexen Typen (einschließlich Auflistungen anderer Auflistungen), nicht nur für Auflistungen von primitiven Typen.  
  
 Die- `ReferencedCollectionTypes` Eigenschaft entspricht dem Schalter **/CollectionType** im Tool Svcutil. exe. Beachten Sie, dass für den Verweis auf mehrere Sammlungs Typen der **/CollectionType** -Schalter mehrmals angegeben werden muss. Wenn sich der Typ nicht in der Datei "mscorlib. dll" befindet, muss auf die Assembly auch mit dem **/Reference** -Schalter verwiesen werden.  
  
#### <a name="import-options-referencing-existing-types"></a>Importoptionen: Verweisen auf vorhandene Typen  
 Gelegentlich entsprechen Typen im Schema vorhandenen .NET Framework Typen, und es ist nicht erforderlich, diese Typen von Grund auf neu zu generieren. (Dieser Abschnitt gilt nur für Typen, bei denen es sich nicht um Auflistungstypen handelt. Auflistungstypen finden Sie im vorherigen Abschnitt.)  
  
 Es kann zum Beispiel sein, dass Sie über einen standardmäßigen unternehmensweiten Datenvertragstyp "Person" verfügen, der beim Darstellen einer Person immer verwendet werden soll. Jedes Mal, wenn ein Dienst diesen Typ verwendet und das dazugehörige Schema in den Dienstmetadaten erscheint, sollten Sie den vorhandenen `Person`-Typ beim Importieren des Schemas wiederverwenden, anstatt für jeden Dienst ein neues Schema zu erstellen.  
  
 Übergeben Sie hierzu eine Liste von .NET Framework Typen, die Sie wieder verwenden möchten, in die Auflistung, die von der- <xref:System.Runtime.Serialization.ImportOptions.ReferencedTypes%2A> Eigenschaft für die-Klasse zurückgegeben wird <xref:System.Runtime.Serialization.ImportOptions> . Falls einige dieser Typen einen Datenvertragsnamen und Namespace aufweisen, der mit dem Namen und Namespace eines Schematyps übereinstimmt, wird ein Strukturvergleich durchgeführt. Wenn festgestellt wird, dass die Typen über übereinstimmende Namen und übereinstimmende Strukturen verfügen, wird der vorhandene .NET Framework Typ wieder verwendet, anstatt einen neuen zu erstellen. Wenn nur der Name übereinstimmt, aber nicht die Struktur, wird eine Ausnahme ausgelöst. Beachten Sie, dass beim Verweisen auf Typen (zum Beispiel beim Hinzufügen von neuen optionalen Datenmembern) kein Spielraum für unterschiedliche Versionen besteht. Die Strukturen müssen genau übereinstimmen.  
  
 Es ist zulässig, der Auflistung der referenzierten Typen mehrere Typen mit demselben Datenvertragsnamen und Namespace hinzuzufügen, solange keine Schematypen mit diesem Namen und Namespace importiert werden. So können Sie der Auflistung alle in einer Assembly enthaltenen Typen auf einfache Weise hinzufügen, ohne sich um Duplikate von Typen kümmern zu müssen, die im Schema eigentlich nicht vorkommen.  
  
 Die- `ReferencedTypes` Eigenschaft entspricht dem Schalter **/Reference** in bestimmten Betriebsmodi des Tools Svcutil. exe.  
  
> [!NOTE]
> Wenn Sie die **Dienstverweis hinzufügen** Tools Svcutil. exe oder (in Visual Studio) verwenden, wird auf alle Typen in "mscorlib. dll" automatisch verwiesen.  
  
#### <a name="import-options-importing-non-datacontract-schema-as-ixmlserializable-types"></a>Importoptionen: Importieren von Nicht-DataContract-Schemas als IXmlSerializable-Typen  
 Der <xref:System.Runtime.Serialization.XsdDataContractImporter> unterstützt eine beschränkte Teilmenge des Schemas. Wenn nicht unterstützte Schemakonstrukte vorhanden sind (zum Beispiel XML-Attribute), schlägt der Importversuch mit einer Ausnahme fehl. Das Festlegen der <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A>-Eigenschaft auf `true` erweitert jedoch den unterstützten Schemabereich. Wenn `true` festgelegt ist, generiert der <xref:System.Runtime.Serialization.XsdDataContractImporter> Typen, die die <xref:System.Xml.Serialization.IXmlSerializable>-Schnittstelle implementieren. Auf diese Weise wird der Direktzugriff auf die XML-Darstellung dieser Typen aktiviert.  
  
##### <a name="design-considerations"></a>Entwurfsaspekte  
  
- Es kann schwierig sein, direkt mit der schwach typisierten XML-Darstellung zu arbeiten. Sie sollten erwägen, eine alternative Serialisierungs-Engine zu verwenden, beispielsweise <xref:System.Xml.Serialization.XmlSerializer>, um mit Schemas arbeiten zu können, die mit stark typisierten Datenverträgen nicht kompatibel sind. Weitere Informationen finden Sie unter [Verwenden der XmlSerializer-Klasse](using-the-xmlserializer-class.md).  
  
- Einige Schemakonstrukte können über <xref:System.Runtime.Serialization.XsdDataContractImporter> nicht importiert werden. Dies ist auch dann nicht möglich, wenn die <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A>-Eigenschaft auf `true` festgelegt ist. Sie sollten auch hierfür erwägen, <xref:System.Xml.Serialization.XmlSerializer> zu verwenden.  
  
- Die genauen Schemas, die unterstützt werden, wenn <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> ist `true` oder `false` in der [Daten Vertrags Schema-Referenz](data-contract-schema-reference.md)beschrieben werden.  
  
- Schemas für generierte <xref:System.Xml.Serialization.IXmlSerializable>-Typen behalten beim Importieren und Exportieren ihre Originaltreue nicht bei. Wenn Sie das Schema also aus den generierten Typen exportieren und jeweils als Klasse importieren, wird nicht das Originalschema zurückgegeben.  
  
 Es ist möglich, die <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A>-Option mit der oben beschriebenen <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A>-Option zu kombinieren. Für Typen, die als <xref:System.Xml.Serialization.IXmlSerializable>-Implementierungen generiert werden müssen, wird beim Verwenden der <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A>-Funktion die Strukturprüfung übersprungen.  
  
 Die <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> Option entspricht dem Schalter **Schalter/importXmlTypes im** im Tool Svcutil. exe.  
  
##### <a name="working-with-generated-ixmlserializable-types"></a>Arbeiten mit generierten IXmlSerializable-Typen  
 Die generierten `IXmlSerializable`-Typen enthalten ein privates Feld mit der Bezeichnung "nodesField", das ein Array mit <xref:System.Xml.XmlNode>-Objekten zurückgibt. Beim Deserialisieren der Instanz eines Typs dieser Art können Sie auf die XML-Daten direkt über dieses Feld zugreifen, indem Sie das XML-Dokumentobjektmodell verwenden. Beim Serialisieren einer Instanz dieses Typs können Sie dieses Feld auf die gewünschten XML-Daten festlegen. Es wird dann serialisiert.  
  
 Dies wird mithilfe der `IXmlSerializable`-Implementierung erreicht. Im generierten `IXmlSerializable`-Typ ruft die <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A>-Implementierung die <xref:System.Runtime.Serialization.XmlSerializableServices.ReadNodes%2A>-Methode der <xref:System.Runtime.Serialization.XmlSerializableServices>-Klasse auf. Bei der Methode handelt es sich um eine Hilfsmethode, die XML-Daten konvertiert, die über einen <xref:System.Xml.XmlReader> für ein Array mit <xref:System.Xml.XmlNode>-Objekten bereitgestellt werden. Die <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A>-Implementierung bewirkt das Gegenteil und konvertiert das Array mit den `XmlNode`-Objekten in eine Folge von <xref:System.Xml.XmlWriter>-Aufrufen. Dies wird durch die Verwendung der <xref:System.Runtime.Serialization.XmlSerializableServices.WriteNodes%2A>-Methode erreicht.  
  
 Es ist möglich, den Schemaexportprozess über die generierten `IXmlSerializable`-Klassen auszuführen. Wie bereits erwähnt, erhalten Sie nicht das ursprüngliche Schema zurück. Stattdessen erhalten Sie den XSD-Standard Typ "anyType", bei dem es sich um einen Platzhalter für einen beliebigen XSD-Typ handelt.  
  
 Dies wird erreicht, indem das <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> -Attribut auf die generierten `IXmlSerializable` Klassen angewendet und eine Methode angegeben wird, die die- <xref:System.Runtime.Serialization.XmlSerializableServices.AddDefaultSchema%2A> Methode aufruft, um den Typ "anyType" zu generieren.  
  
> [!NOTE]
> Der <xref:System.Runtime.Serialization.XmlSerializableServices>-Typ ist nur vorhanden, um diese Funktion zu unterstützen. Es ist nicht ratsam, den Typ zu einem anderen Zweck zu verwenden.  
  
#### <a name="import-options-advanced-options"></a>Importoptionen: Erweiterte Optionen  
 Bei den folgenden Optionen handelt es sich um erweiterte Importoptionen:  
  
- <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A>-Eigenschaft. Geben Sie den <xref:System.CodeDom.Compiler.CodeDomProvider> an, der verwendet werden soll, um den Code für die generierten Klassen zu generieren. Der Importmechanismus versucht, Funktionen zu vermeiden, die der <xref:System.CodeDom.Compiler.CodeDomProvider> nicht unterstützt. Wenn <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A> nicht festgelegt ist, wird der vollständige Satz .NET Framework Features ohne Einschränkungen verwendet.  
  
- <xref:System.Runtime.Serialization.ImportOptions.DataContractSurrogate%2A>-Eigenschaft. Mit dieser Eigenschaft können Sie eine <xref:System.Runtime.Serialization.IDataContractSurrogate>-Implementierung angeben. <xref:System.Runtime.Serialization.IDataContractSurrogate> passt den Importprozess an. Weitere Informationen finden Sie unter [Data Contract Surrogates](../extending/data-contract-surrogates.md). Standardmäßig wird kein Ersatzzeichen verwendet.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.XsdDataContractImporter>
- <xref:System.Runtime.Serialization.XsdDataContractExporter>
- <xref:System.Runtime.Serialization.ImportOptions>
- [Datenvertrags-Schemareferenz](data-contract-schema-reference.md)
- [Datenvertrag-Ersatzzeichen](../extending/data-contract-surrogates.md)
- [Import und Export von Schemas](schema-import-and-export.md)
- [Exportieren von Schemas aus Klassen](exporting-schemas-from-classes.md)
- [Datenvertrags-Schemareferenz](data-contract-schema-reference.md)
