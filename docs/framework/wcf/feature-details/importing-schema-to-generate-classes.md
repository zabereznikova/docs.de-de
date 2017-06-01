---
title: "Importieren von Schemas zum Generieren von Klassen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, Import und Export von Schemas"
  - "XsdDataContractImporter-Klasse"
ms.assetid: b9170583-8c34-43bd-97bb-6c0c8dddeee0
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Importieren von Schemas zum Generieren von Klassen
Zum Generieren von Klassen aus Schemas, die mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], verwenden Sie die <xref:System.Runtime.Serialization.XsdDataContractImporter> Klasse. In diesem Thema werden der Prozess und die Variationen beschrieben.  
  
## <a name="the-import-process"></a>Der Importprozess  
 Der schemaimportprozess beginnt mit einem <xref:System.Xml.Schema.XmlSchemaSet> und erzeugt eine <xref:System.CodeDom.CodeCompileUnit>.  
  
 `XmlSchemaSet` ist Teil des SOM (Schemaobjektmodell) von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], das eine Gruppe von XSD-Schemadokumenten (XML Schema Definition Language) darstellt. Erstellen einer `XmlSchemaSet` -Objekt aus einer Gruppe von XSD-Dokumenten, deserialisieren Sie jedes Dokument in ein <xref:System.Xml.Schema.XmlSchema> Objekt (mit der <xref:System.Xml.Serialization.XmlSerializer>) und fügen Sie diese Objekte einem neuen `XmlSchemaSet`.  
  
 `CodeCompileUnit` ist Teil des CodeDOM (Code-Dokumentobjektmodell) von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], das den [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Code abstrakt darstellt. Generieren Sie den eigentlichen Code aus einer `CodeCompileUnit`, verwenden Sie eine Unterklasse von der <xref:System.CodeDom.Compiler.CodeDomProvider> Klasse, z. B. die <xref:Microsoft.CSharp.CSharpCodeProvider> oder <xref:Microsoft.VisualBasic.VBCodeProvider> Klasse.  
  
#### <a name="to-import-a-schema"></a>So importieren Sie ein Schema  
  
1.  Erstellen Sie eine Instanz der <xref:System.Runtime.Serialization.XsdDataContractImporter>.  
  
2.  Optional. Übergeben Sie im Konstruktor eine `CodeCompileUnit`. Die während des Schemaimports generierten Typen werden dieser `CodeCompileUnit`-Instanz hinzugefügt. Es wird keine leere `CodeCompileUnit` verwendet.  
  
3.  Optional. Rufen Sie eine von der <xref:System.Runtime.Serialization.XsdDataContractImporter.CanImport%2A> Methoden. Die Methode bestimmt, ob es sich beim jeweiligen Schema um ein gültiges Datenvertragsschema handelt und ob es importiert werden kann. Die `CanImport`-Methode verfügt über die gleichen Überladungen wie `Import` (der nächste Schritt).  
  
4.  Rufen Sie eine der überladenen `Import` Methoden, z. B. die <xref:System.Runtime.Serialization.XsdDataContractImporter.Import%28System.Xml.Schema.XmlSchemaSet%29> Methode.  
  
     Bei der einfachsten Überladung wird ein `XmlSchemaSet` verwendet, und es werden alle Typen importiert, die im Schemasatz enthalten sind, einschließlich anonyme Typen. Anderen Überladungen können Sie den XSD-Typ oder eine Liste der Typen importieren angeben (in Form einer <xref:System.Xml.XmlQualifiedName> oder eine Auflistung von `XmlQualifiedName` Objekte). In diesem Fall werden nur die angegebenen Typen importiert. Eine Überladung verwendet ein <xref:System.Xml.Schema.XmlSchemaElement> importiert ein bestimmtes Element aus der `XmlSchemaSet`, einschließlich des dazugehörigen Typs (anonym oder nicht anonym). Diese Überladung gibt einen `XmlQualifiedName` zurück, der für den Datenvertragsnamen des Typs steht, der für dieses Element generiert wurde.  
  
     Mehrere Aufrufe der `Import`-Methode führen dazu, dass mehrere Elemente derselben `CodeCompileUnit` hinzugefügt werden. Ein Typ wird nicht für den `CodeCompileUnit` generiert, wenn er darin bereits vorhanden ist. Rufen Sie `Import` für einen `XsdDataContractImporter` mehrfach auf, anstatt mehrere `XsdDataContractImporter`-Objekte zu verwenden. Dies ist die empfohlene Möglichkeit, um die Generierung von doppelten Typen zu vermeiden.  
  
    > [!NOTE]
    >  Wenn beim Importieren ein Fehler auftritt, befindet sich die `CodeCompileUnit` in einem unvorhersehbaren Zustand. Wenn Sie eine `CodeCompileUnit` verwenden, die aus einem fehlgeschlagenen Import stammt, kann Sie dies ggf. anfällig für Sicherheitslücken machen.  
  
5.  Zugriff der `CodeCompileUnit` über die <xref:System.Runtime.Serialization.XsdDataContractImporter.CodeCompileUnit%2A> Eigenschaft.  
  
### <a name="import-options-customizing-the-generated-types"></a>Importoptionen: Anpassen der generierten Typen  
 Lassen sich die <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> Eigenschaft der <xref:System.Runtime.Serialization.XsdDataContractImporter> mit einer Instanz von der <xref:System.Runtime.Serialization.ImportOptions> Klasse, um verschiedene Aspekte des Importprozesses zu steuern. Verschiedene Optionen wirken sich direkt auf die generierten Typen aus.  
  
#### <a name="controlling-the-access-level-generateinternal-or-the-internal-switch"></a>Steuern der Zugriffsebene (GenerateInternal oder der Schalter "/internal")  
 Dies entspricht der **/ interne** wechseln Sie auf die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
 Normalerweise werden öffentliche Typen aus Schemas generiert, indem private Felder und passende Eigenschaften öffentlicher Datenmember verwendet werden. Um stattdessen interne Typen generieren möchten, legen Sie die <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> -Eigenschaft `true`.  
  
 Das folgende Beispiel zeigt ein Schema transformiert in eine interne Klasse, wenn die <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> -Eigenschaft auf festgelegt ist`true.`  
  
 [!code-csharp[c_SchemaImportExport#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#2)]
 [!code-vb[c_SchemaImportExport#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#2)]  
  
#### <a name="controlling-namespaces-namespaces-or-the-namespace-switch"></a>Steuern von Namespaces (Namespaces oder der Schalter "/namespace")  
 Dies entspricht der **/Namespace** schalten die `Svcutil.exe` Tool.  
  
 Normalerweise werden aus dem Schema generierte Typen generiert, in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Namespaces mit jedem XSD-Namespace, die entsprechend einer bestimmten [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Namespace in der beschriebenen Zuordnung [Datenvertrags-Schemareferenz](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Sie können diese Zuordnung durch Anpassen der <xref:System.Runtime.Serialization.ImportOptions.Namespaces%2A> Eigenschaft, um ein <xref:System.Collections.Generic.Dictionary%602>.\</TKey, TValue> Wenn ein bestimmter XSD-Namespace im Wörterbuch enthalten ist, wird auch der entsprechende [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Namespace aus Ihrem Wörterbuch verwendet.  
  
 Betrachten Sie zum Beispiel das folgende Schema:  
  
 <!-- TODO: review snippet reference [!code[c_SchemaImportExport#10](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#10)]  -->  
  
 Im folgenden Beispiel wird die `Namespaces`-Eigenschaft verwendet, um den http://schemas.contoso.com/carSchema-Namespace "Contoso.Cars" zuzuordnen.  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
#### <a name="adding-the-serializableattribute-generateserializable-or-the-serializable-switch"></a>Hinzufügen von SerializableAttribute (GenerateSerializable oder der Schalter "/serializable")  
 Dies entspricht der **/ serializable** schalten die `Svcutil.exe` Tool.  
  
 Manchmal ist es wichtig, dass die aus dem Schema generierten Typen mit verwendet werden [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Laufzeitmodule Serialisierung (z. B. die <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> und <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> Klassen). Dies ist hilfreich, wenn Sie Typen für das [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Remoting nutzen. Um dies zu ermöglichen, müssen Sie anwenden der <xref:System.SerializableAttribute> -Attribut auf die generierten Typen zusätzlich zum normalen <xref:System.Runtime.Serialization.DataContractAttribute> Attribut. Das Attribut wird automatisch generiert, wenn die Importoption `GenerateSerializable` auf `true` festgelegt ist.  
  
 Das folgende Beispiel zeigt die `Vehicle`-Klasse, bei deren Generierung die Importoption `GenerateSerializable` auf `true` festgelegt ist.  
  
 [!code-csharp[c_SchemaImportExport#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#4)]
 [!code-vb[c_SchemaImportExport#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#4)]  
  
#### <a name="adding-data-binding-support-enabledatabinding-or-the-enabledatabinding-switch"></a>Hinzufügen von Datenbindungsunterstützung (EnableDataBinding oder der Schalter „/enableDataBinding“)  
 Dies entspricht der **/enableDataBinding** Tool Svcutil.exe wechseln.  
  
 In einigen Fällen kann es ratsam sein, die aus dem Schema generierten Typen an Komponenten der grafischen Benutzeroberfläche zu binden, damit die Aktualisierungen der Instanzen dieser Typen automatisch auf der Benutzeroberfläche widergespiegelt werden. Die `XsdDataContractImporter` -Typen, die implementieren Generieren der <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle so, dass es sich bei jeder Änderung der Eigenschaft ein Ereignis auslöst. Beim Generieren von Typen für die Verwendung mit einer Client-UI-Programmierumgebung, die diese Schnittstelle unterstützt (z. B. [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)]), legen die <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> -Eigenschaft `true` zum Aktivieren dieser Funktion.  
  
 Das folgende Beispiel zeigt die `Vehicle` Klasse generiert, mit der <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> festgelegt `true`.  
  
 [!code-csharp[C_SchemaImportExport#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#5)]
 [!code-vb[C_SchemaImportExport#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#5)]  
  
### <a name="import-options-choosing-collection-types"></a>Importoptionen: Wählen von Auflistungstypen  
 Zwei spezielle XML-Muster stellen Auflistungen von Elementen dar: Listen mit Elementen und Zuordnungen zwischen einem Element und einem anderen. Unten ist ein Beispiel für eine Liste mit Zeichenfolgen angegeben.  
  
 <!-- TODO: review snippet reference [!code[C_SchemaImportExport#11](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#11)]  -->  
  
 Das folgende Beispiel zeigt eine Zuordnung zwischen einer Zeichenfolge und einer Ganzzahl (`city name` und `population`).  
  
 <!-- TODO: review snippet reference [!code[C_SchemaImportExport#12](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#12)]  -->  
  
> [!NOTE]
>  Jede Zuordnung kann auch als Liste angesehen werden. Sie können die oben angegebene Zuordnung zum Beispiel als Liste mit komplexen `city`-Objekten ansehen, die zwei Felder aufweisen (ein Zeichenfolgenfeld und ein Ganzzahlfeld). Beide Muster verfügen im XSD-Schema über eine Darstellung. Es ist nicht möglich, zwischen einer Liste und einer Zuordnung zu unterscheiden. Aus diesem Grund werden Muster dieser Art immer wie Listen behandelt, es sei denn, das Schema enthält eine bestimmte [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-spezifische Anmerkung. Die Anmerkung gibt an, dass ein bestimmtes Muster eine Zuordnung darstellt. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Datenvertrags-Schemareferenz](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).  
  
 In der Regel wird eine Liste als Auflistungsdatenvertrag importiert, der von einer generischen Liste oder einem [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Array abgeleitet ist. Dies hängt davon ab, ob das Schema das standardmäßige Namensmuster für Auflistungen verwendet. Dies wird ausführlicher beschrieben [Sammlungstypen in Datenverträgen](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md). Zuordnungen werden normalerweise entweder als ein <xref:System.Collections.Generic.Dictionary%602> oder auflistungsdatenvertrag, die vom Wörterbuchobjekt abgeleitet ist.\</TKey, TValue> Betrachten Sie zum Beispiel das folgende Schema:  
  
 <!-- TODO: review snippet reference [!code[c_SchemaImportExport#13](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#13)]  -->  
  
 Der Import wird hierbei wie folgt durchgeführt (aus Gründen der besseren Lesbarkeit werden anstelle von Eigenschaften Felder angezeigt).  
  
 [!code-csharp[c_SchemaImportExport#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#6)]
 [!code-vb[c_SchemaImportExport#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#6)]  
  
 Es ist möglich, die Auflistungstypen anzupassen, die für Schemamuster dieser Art generiert werden. Sie möchten z. B. Ableiten von Auflistungen Generieren der <xref:System.ComponentModel.BindingList%601> statt der <xref:System.Collections.Generic.List%601> Klasse, um die Typen in ein Listenfeld zu binden, und es werden automatisch aktualisiert, wenn der Inhalt der Auflistung ändern. Legen Sie hierzu die <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> Eigenschaft der <xref:System.Runtime.Serialization.ImportOptions> Klasse, um eine Liste der Auflistungstypen (im weiteren als referenzierten Typen bezeichnet) verwendet werden. Beim Importieren von Auflistungen wird diese Liste mit Verweisen zu Auflistungstypen durchsucht und die Auflistung mit der höchsten Übereinstimmung verwendet, falls vorhanden. Zuordnungen nur für Typen, die generische oder die nicht generische Implementierung, Übereinstimmungen <xref:System.Collections.IDictionary> Schnittstelle, während alle unterstützten Auflistungstypen Listen gegenübergestellt werden.  
  
 Z. B. wenn die <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> -Eigenschaft auf festgelegt ist ein <xref:System.ComponentModel.BindingList%601>, `people` Typ im vorherigen Beispiel wie folgt generiert.  
  
 [!code-csharp[C_SchemaImportExport#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#7)]
 [!code-vb[C_SchemaImportExport#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#7)]  
  
 Ein geschlossener generischer Typ wird als beste Übereinstimmung betrachtet. Zum Beispiel wenn die Typen `BindingList(Of Integer)` und <xref:System.Collections.ArrayList> übergeben werden in die Auflistung der referenzierten Typen werden alle Listen mit Ganzzahlen, die im Schema als importiert eine `BindingList(Of Integer)`. Alle anderen Listen, zum Beispiel `List(Of String)`, werden als `ArrayList` importiert.  
  
 Wenn ein Typ, der die generische `IDictionary`-Schnittstelle implementiert, der Auflistung der referenzierten Typen hinzugefügt wird, müssen ihre Typparameter entweder vollständig offen oder vollständig geschlossen sein.  
  
 Duplikate sind nicht zulässig. Zum Beispiel können Sie den referenzierten Typen nicht sowohl eine `List(Of Integer)` als auch eine `Collection(Of Integer)` hinzufügen. In diesem Fall wäre es unmöglich zu bestimmen, welches Element verwendet werden soll, wenn im Schema eine Liste mit Ganzzahlen gefunden wird. Duplikate werden nur erkannt, wenn es einen Typ im Schema gibt, der das Duplikatproblem offenlegt. Wenn das importierte Schema zum Beispiel keine Listen mit Ganzzahlen enthält, ist es zulässig, sowohl die `List(Of Integer)` als auch die `Collection(Of Integer)` in der Auflistung mit den referenzierten Typen zu verwenden, aber beide haben keine Auswirkung.  
  
 Der Mechanismus mit den referenzierten Auflistungstypen funktioniert ebenso gut für Auflistungen mit komplexen Typen (einschließlich Auflistungen anderer Auflistungen), nicht nur für Auflistungen von primitiven Typen.  
  
 Die `ReferencedCollectionTypes` Eigenschaft entspricht der **/collectionType** Tool SvcUtil.exe wechseln. Beachten Sie, dass mehrere Auflistungstypen verweisen die **/collectionType** Switch mehrmals angegeben werden muss. Wenn der Typ nicht in der Datei mscorlib.dll enthalten ist, die Assembly muss auch verwiesen werden mithilfe der **/reference** wechseln.  
  
#### <a name="import-options-referencing-existing-types"></a>Importoptionen: Verweisen auf vorhandene Typen  
 In einigen Fällen entsprechen Typen im Schema vorhandenen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typen, und es ist nicht erforderlich, diese Typen ganz neu zu generieren. (Dieser Abschnitt gilt nur für Typen, bei denen es sich nicht um Auflistungstypen handelt. Auflistungstypen finden Sie im vorherigen Abschnitt.)  
  
 Es kann zum Beispiel sein, dass Sie über einen standardmäßigen unternehmensweiten Datenvertragstyp "Person" verfügen, der beim Darstellen einer Person immer verwendet werden soll. Jedes Mal, wenn ein Dienst diesen Typ verwendet und das dazugehörige Schema in den Dienstmetadaten erscheint, sollten Sie den vorhandenen `Person`-Typ beim Importieren des Schemas wiederverwenden, anstatt für jeden Dienst ein neues Schema zu erstellen.  
  
 Hierzu übergeben Sie eine Liste der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Typen, die Sie wiederverwenden, an die Auflistung möchten der <xref:System.Runtime.Serialization.ImportOptions.ReferencedTypes%2A> -Eigenschaft zurückgibt, auf die <xref:System.Runtime.Serialization.ImportOptions> Klasse. Falls einige dieser Typen einen Datenvertragsnamen und Namespace aufweisen, der mit dem Namen und Namespace eines Schematyps übereinstimmt, wird ein Strukturvergleich durchgeführt. Wenn ermittelt wird, dass die Typen über übereinstimmende Namen und Strukturen verfügen, wird der vorhandene [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typ wiederverwendet und kein neuer Typ generiert. Wenn nur der Name übereinstimmt, aber nicht die Struktur, wird eine Ausnahme ausgelöst. Beachten Sie, dass beim Verweisen auf Typen (zum Beispiel beim Hinzufügen von neuen optionalen Datenmembern) kein Spielraum für unterschiedliche Versionen besteht. Die Strukturen müssen genau übereinstimmen.  
  
 Es ist zulässig, der Auflistung der referenzierten Typen mehrere Typen mit demselben Datenvertragsnamen und Namespace hinzuzufügen, solange keine Schematypen mit diesem Namen und Namespace importiert werden. So können Sie der Auflistung alle in einer Assembly enthaltenen Typen auf einfache Weise hinzufügen, ohne sich um Duplikate von Typen kümmern zu müssen, die im Schema eigentlich nicht vorkommen.  
  
 Die `ReferencedTypes` Eigenschaft entspricht der **/reference** bei bestimmten Verwendungsarten des Tools Svcutil.exe wechseln.  
  
> [!NOTE]
>  Bei Verwendung von Svcutil.exe oder (im [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]) der **Hinzufügen eines Dienstverweises** verwenden, alle Typen in der Datei MsCorLib.dll automatisch referenziert.  
  
#### <a name="import-options-importing-non-datacontract-schema-as-ixmlserializable-types"></a>Importoptionen: Importieren von Nicht-DataContract-Schemas als IXmlSerializable-Typen  
 Die <xref:System.Runtime.Serialization.XsdDataContractImporter> unterstützt eine beschränkte Teilmenge des Schemas. Wenn nicht unterstützte Schemakonstrukte vorhanden sind (zum Beispiel XML-Attribute), schlägt der Importversuch mit einer Ausnahme fehl. Festlegen der <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> -Eigenschaft `true` erweitert den Bereich des Schemas unterstützt. Bei Festlegung auf `true`, <xref:System.Runtime.Serialization.XsdDataContractImporter> generiert Typen, implementieren die <xref:System.Xml.Serialization.IXmlSerializable> Schnittstelle. Auf diese Weise wird der Direktzugriff auf die XML-Darstellung dieser Typen aktiviert.  
  
##### <a name="design-considerations"></a>Entwurfsüberlegungen  
  
-   Es kann schwierig sein, direkt mit der schwach typisierten XML-Darstellung zu arbeiten. Erwägen Sie ein alternatives Serialisierungsmodul, wie z. B. die <xref:System.Xml.Serialization.XmlSerializer>, um mit Schemas, die nicht kompatibel mit Verträgen mit starker Typisierung arbeiten. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Verwenden der XmlSerializer-Klasse](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).  
  
-   Einige Schemakonstrukte können nicht importiert werden, indem die <xref:System.Runtime.Serialization.XsdDataContractImporter> , auch wenn die <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> -Eigenschaft auf festgelegt ist `true`. In diesem Fall sollten Sie mithilfe der <xref:System.Xml.Serialization.XmlSerializer> in solchen Fällen.  
  
-   Die genauen Schemakonstrukte, die unterstützt sowohl beim <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> ist `true` oder `false` in beschriebenen [Datenvertrags-Schemareferenz](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).  
  
-   Schemas für generierte <xref:System.Xml.Serialization.IXmlSerializable> werden Typen nicht beibehalten Genauigkeit beim importiert und exportiert werden. Wenn Sie das Schema also aus den generierten Typen exportieren und jeweils als Klasse importieren, wird nicht das Originalschema zurückgegeben.  
  
 Es ist möglich, kombinieren Sie die <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> -Option mit der <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A> zuvor beschriebene Option. Für Typen, die als generiert <xref:System.Xml.Serialization.IXmlSerializable> Implementierungen, die strukturelle Überprüfung wird übersprungen, wenn mit der <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A> Funktion.  
  
 Die <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> Option entspricht der **/importXmlTypes** Tool Svcutil.exe wechseln.  
  
##### <a name="working-with-generated-ixmlserializable-types"></a>Arbeiten mit generierten IXmlSerializable-Typen  
 Die generierte `IXmlSerializable` Typen enthalten ein privates Feld mit der Bezeichnung "NodesField", die gibt ein Array von <xref:System.Xml.XmlNode> Objekte. Beim Deserialisieren der Instanz eines Typs dieser Art können Sie auf die XML-Daten direkt über dieses Feld zugreifen, indem Sie das XML-Dokumentobjektmodell verwenden. Beim Serialisieren einer Instanz dieses Typs können Sie dieses Feld auf die gewünschten XML-Daten festlegen. Es wird dann serialisiert.  
  
 Dies wird mithilfe der `IXmlSerializable`-Implementierung erreicht. In der generierten `IXmlSerializable` Typ, der <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> Implementierung ruft die <xref:System.Runtime.Serialization.XmlSerializableServices.ReadNodes%2A> Methode der <xref:System.Runtime.Serialization.XmlSerializableServices> Klasse. Die Methode ist eine Hilfsmethode, die durch bereitgestellten XML-Daten konvertiert ein <xref:System.Xml.XmlReader> in ein Array von <xref:System.Xml.XmlNode> Objekte. Die <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> Implementierung bewirkt das Gegenteil und konvertiert das Array mit `XmlNode` Objekte in eine Sequenz von <xref:System.Xml.XmlWriter> aufrufen. Dies geschieht mithilfe der <xref:System.Runtime.Serialization.XmlSerializableServices.WriteNodes%2A> Methode.  
  
 Es ist möglich, den Schemaexportprozess über die generierten `IXmlSerializable`-Klassen auszuführen. Wie bereits erwähnt, erhalten Sie nicht das ursprüngliche Schema zurück. Stattdessen erhalten Sie den standardmäßigen XSD-Typ "anyType" zurück, der ein Platzhalter für einen beliebigen XSD-Typ ist.  
  
 Dies erfolgt durch Anwenden der <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> -Attribut auf die generierten `IXmlSerializable` Klassen und gibt eine Methode aufruft, die <xref:System.Runtime.Serialization.XmlSerializableServices.AddDefaultSchema%2A> Methode, um den Typ "AnyType" zu generieren.  
  
> [!NOTE]
>  Die <xref:System.Runtime.Serialization.XmlSerializableServices> Typ vorhanden ist, ausschließlich, um diese Funktion zu unterstützen. Es ist nicht ratsam, den Typ zu einem anderen Zweck zu verwenden.  
  
#### <a name="import-options-advanced-options"></a>Importoptionen: Erweiterte Optionen  
 Bei den folgenden Optionen handelt es sich um erweiterte Importoptionen:  
  
-   <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A> Eigenschaft. Geben Sie die <xref:System.CodeDom.Compiler.CodeDomProvider> zu verwenden, um den Code für die generierten Klassen zu generieren. Der Importmechanismus versucht, vermeiden Sie Funktionen, die <xref:System.CodeDom.Compiler.CodeDomProvider> nicht unterstützt. Zum Beispiel unterstützt die Programmiersprache J# keine Generika. Wenn Sie den J#-Codeanbieter in dieser Eigenschaft angeben, wird keine generischen Typen in des Importer generiert <xref:System.CodeDom.CodeCompileUnit>. Wenn die <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A> nicht festgelegt ist, den vollständigen Satz von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Funktionen ohne Einschränkungen verwendet.  
  
-   <xref:System.Runtime.Serialization.ImportOptions.DataContractSurrogate%2A> Eigenschaft. Ein <xref:System.Runtime.Serialization.IDataContractSurrogate> Implementierung kann mit dieser Eigenschaft angegeben werden. Die <xref:System.Runtime.Serialization.IDataContractSurrogate> passt den Importprozess an. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Datenvertrag-Ersatzzeichen](../../../../docs/framework/wcf/extending/data-contract-surrogates.md). Standardmäßig wird kein Ersatzzeichen verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.Runtime.Serialization.XsdDataContractImporter>   
 <xref:System.Runtime.Serialization.XsdDataContractExporter>   
 <xref:System.Runtime.Serialization.ImportOptions>   
 [Datenvertrags-Schemareferenz](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)   
 [Datenvertrag-Ersatzzeichen](../../../../docs/framework/wcf/extending/data-contract-surrogates.md)   
 [Schema importieren und exportieren](../../../../docs/framework/wcf/feature-details/schema-import-and-export.md)   
 [Exportieren von Schemas aus Klassen](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)   
 [Datenvertrags-Schemareferenz](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)