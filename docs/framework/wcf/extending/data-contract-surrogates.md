---
title: Datenvertrag-Ersatzzeichen
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], surrogates
ms.assetid: 8c31134c-46c5-4ed7-94af-bab0ac0dfce5
ms.openlocfilehash: e33a487c03bbf87666d517040e00131f5482be6f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251515"
---
# <a name="data-contract-surrogates"></a>Datenvertrag-Ersatzzeichen

Das Datenvertrag- *Ersatz* Zeichen ist eine erweiterte Funktion, die auf dem Daten Vertragsmodell basiert. Diese Funktion wurde zur Verwendung für die Typanpassung und -ersetzung entwickelt, wenn Benutzer Änderungen daran vornehmen möchten, wie ein Typ serialisiert, deserialisiert oder in Metadaten projiziert wird. Einige Szenarien, in denen ein Ersatzzeichen verwendet werden kann, sind die fehlende Spezifizierung eines Datenvertrags für den Typ, die fehlende Markierung von Feldern und Eigenschaften mit dem <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut oder wenn Benutzer die dynamische Erstellung von Schemavarianten wünschen.  
  
 Serialisierung und Deserialisierung werden mit dem Datenvertrag-Ersatzzeichen erreicht, wenn <xref:System.Runtime.Serialization.DataContractSerializer> zum Konvertieren aus .NET Framework in ein geeignetes Format, wie z. B. XML, verwendet wird. Das Datenvertrag-Ersatzzeichen kann auch verwendet werden, um die für Typen exportierten Metadaten zu ändern, wenn Metadatendarstellungen, wie z. B. XML Schema Documents (XSD), erstellt werden. Beim Importieren wird der Code aus den Metadaten erstellt, und das Ersatzzeichen kann in diesem Fall verwendet werden, um auch den generierten Code anzupassen.  
  
## <a name="how-the-surrogate-works"></a>So funktioniert das Ersatzzeichen  

 Ein Ersatzzeichen funktioniert, indem es einen Typ (den "ursprünglichen" Typ) einem anderen Typ (dem "ersetzten" Typ) zuordnet. Im folgenden Beispiel werden der ursprüngliche Typ `Inventory` und ein neuer Ersatzzeichen-`InventorySurrogated`-Typ veranschaulicht. Der Typ `Inventory` ist nicht serialisierbar, aber der Typ `InventorySurrogated` ist serialisierbar:  
  
 [!code-csharp[C_IDataContractSurrogate#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#1)]  
  
 Weil für diese Klasse kein Datenvertrag definiert wurde, soll die Klasse in eine Ersatzzeichenklasse mit einem Datenvertrag konvertiert werden. Die ersetzte Klasse wird im folgenden Beispiel gezeigt:  
  
 [!code-csharp[C_IDataContractSurrogate#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#2)]  
  
## <a name="implementing-the-idatacontractsurrogate"></a>Implementieren des IDataContractSurrogate  

 Zur Verwendung des Datenvertrag-Ersatzzeichens implementieren Sie die <xref:System.Runtime.Serialization.IDataContractSurrogate>-Schnittstelle.  
  
 Es folgt eine Übersicht über jede Methode von <xref:System.Runtime.Serialization.IDataContractSurrogate> mit einer möglichen Implementierung.  
  
### <a name="getdatacontracttype"></a>GetDataContractType  

 Die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%2A>-Methode ordnet einen Typ einem anderen zu. Diese Methode ist für Serialisierung, Deserialisierung, Import und Export erforderlich.  
  
 Die erste Aufgabe definiert, welche Typen anderen Typen zugeordnet werden. Beispiel:  
  
 [!code-csharp[C_IDataContractSurrogate#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#3)]  
  
- Bei der Serialisierung wird die durch diese Methode zurückgegebene Zuordnung verwendet, um die ursprüngliche Instanz in eine ersetzte Instanz zu transformieren, indem die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%2A>-Methode aufgerufen wird.  
  
- Bei der Deserialisierung wird die durch diese Methode zurückgegebene Zuordnung durch das Serialisierungsprogramm verwendet, um die Deserialisierung in eine Instanz des Ersatzzeichentyps durchzuführen. Es ruft anschließend <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%2A> auf, um die ersetzte Instanz in eine Instanz des ursprünglichen Typs zu transformieren.  
  
- Beim Export wird der durch diese Methode zurückgegebene Ersatzzeichentyp reflektiert, um den Datenvertrag zu erhalten, der zur Generierung von Metadaten verwendet werden soll.  
  
- Beim Import wird der Ausgangstyp in einen Ersatzzeichentyp geändert und reflektiert, um den Datenvertrag, der für Zwecke wie den Support-Verweis verwendet werden soll, zu erhalten.  
  
 Der <xref:System.Type>-Parameter ist der Typ des Objekts, das serialisiert, deserialisiert, importiert oder exportiert wird. Die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%2A>-Methode muss den Eingabetyp zurückgeben, wenn das Ersatzzeichen den Typ nicht behandelt. Ansonsten wird der entsprechende Ersatzzeichentyp zurückgegeben. Wenn mehrere Ersatzzeichentypen vorhanden sind, können zahlreiche Zuordnungen in dieser Methode definiert werden.  
  
 Die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%2A>-Methode wird nicht für integrierte Datenvertragsprimitiven, z. B. <xref:System.Int32> oder <xref:System.String>, aufgerufen. Für andere Typen, wie z. B. Arrays, benutzerdefinierte Typen und andere Datenstrukturen, wird diese Methode für jeden Typ aufgerufen.  
  
 Beim vorherigen Beispiel überprüft die Methode, ob der `type`-Parameter und `Inventory` vergleichbar sind. Wenn das der Fall ist, führt die Methode eine Zuordnung zu `InventorySurrogated` durch. Bei jedem Aufrufen einer Serialisierung, einer Deserialisierung, eines Importschemas oder eines Exportschemas wird diese Funktion zuerst aufgerufen, um die Zuordnung zwischen den Typen zu ermitteln.  
  
### <a name="getobjecttoserialize-method"></a>GetObjectToSerialize-Methode  

 Die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%2A>-Methode konvertiert die Instanz des ursprünglichen Typs in die Instanz des Ersatzzeichentyps. Die Methode ist für die Serialisierung erforderlich.  
  
 Der nächste Schritt besteht darin zu definieren, wie die physikalischen Daten von der ursprünglichen Instanz zur Ersatzzeicheninstanz erfolgen soll, indem die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%2A>-Methode implementiert wird. Beispiel:  
  
 [!code-csharp[C_IDataContractSurrogate#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#4)]  
  
 Die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%2A>-Methode wird aufgerufen, wenn ein Objekt serialisiert wird. Diese Methode überträgt Daten vom ursprünglichen Typ auf die Felder des Ersatzzeichentyps. Die Felder können den Ersatzzeichenfeldern direkt zugeordnet werden, oder in dem Ersatzzeichen können Bearbeitungen der ursprünglichen Daten gespeichert werden. Zu den Verwendungsmöglichkeiten zählen: direktes Zuordnen der Felder, Durchführen von Vorgängen an den Daten, die in den Ersatzzeichenfeldern gespeichert werden sollen, oder Speichern der XML des ursprünglichen Typs in dem Ersatzzeichenfeld.  
  
 Der `targetType`-Parameter verweist auf den deklarierten Typ des Members. Dieser Parameter ist der Ersatzzeichentyp, der durch die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%2A>-Methode zurückgegeben wird. Vom Serialisierungsprogramm wird nicht erzwungen, dass das zurückgegebene Objekt diesem Typ zugeordnet werden kann. Der `obj` -Parameter ist das zu serialisierende Objekt und wird bei Bedarf in seinen Ersatz Zeichen konvertiert. Diese Methode muss den Eingabeobjekttyp zurückgeben, wenn das Ersatzzeichen das Objekt nicht behandelt. Andernfalls wird das neue Ersatzzeichenobjekt zurückgegeben. Das Ersatzzeichen wird nicht aufgerufen, wenn das Objekt NULL ist. Innerhalb dieser Methode werden möglicherweise zahlreiche Ersatzzeichenzuordnungen für verschiedene Instanzen definiert.  
  
 Wenn Sie ein <xref:System.Runtime.Serialization.DataContractSerializer> erstellen, können Sie es anweisen, Objektverweise beizubehalten. (Weitere Informationen finden Sie unter [Serialisierung und Deserialisierung](../feature-details/serialization-and-deserialization.md).) Dies erfolgt durch Festlegen des- `preserveObjectReferences` Parameters im Konstruktor auf `true` . In diesem Fall wird das Ersatzzeichen für ein Objekt nur ein einziges Mal aufgerufen, weil alle nachfolgenden Serialisierungen lediglich den Verweis in den Stream schreiben. Wenn `preserveObjectReferences` auf `false` festgelegt wird, dann wird das Ersatzzeichen jedes Mal aufgerufen, wenn eine Instanz gefunden wird.  
  
 Wenn der Typ der serialisierten Instanz vom deklarierten Typ abweicht, werden Typinformationen in den Stream geschrieben, z. B. `xsi:type`, um die Deserialisierung der Instanz am anderen Ende zu ermöglichen. Dieser Prozess tritt unabhängig davon auf, ob das Objekt ersetzt wurde oder nicht.  
  
 Das obige Beispiel konvertiert die Daten der `Inventory`-Instanz zu denen von `InventorySurrogated`. Es überprüft den Objekttyp und führt die erforderlichen Bearbeitungen durch, um die Konvertierung in den Ersatzzeichentyp zu bewirken. In diesem Fall werden die Felder der `Inventory`-Klasse direkt über die Felder der `InventorySurrogated`-Klasse kopiert.  
  
### <a name="getdeserializedobject-method"></a>GetDeserializedObject-Methode  

 Die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%2A>-Methode konvertiert die Ersatzzeichentypinstanz in die Instanz des ursprünglichen Typs. Sie ist für die Deserialisierung erforderlich.  
  
 Die nächste Aufgabe besteht darin zu definieren, wie die physikalischen Daten von der Ersatzzeicheninstanz zur ursprünglichen Instanz zugeordnet werden sollen. Beispiel:  
  
 [!code-csharp[C_IDataContractSurrogate#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#5)]  
  
 Diese Methode wird nur während der Deserialisierung eines Objekts aufgerufen. Sie sorgt für die umgekehrte Datenzuordnung für die Deserialisierung vom Ersatzzeichentyp zum ursprünglichen Typ. Wie bei der `GetObjectToSerialize`-Methode gehören zu den Anwendungsmöglichkeiten das direkte Austauschen von Felddaten, das Durchführen von Vorgängen an den Daten und das Speichern der XML-Daten. Aufgrund von Änderungen während der Datenkonvertierung ergibt die Deserialisierung möglicherweise nicht immer die exakten Datenwerte aus dem Original.  
  
 Der `targetType`-Parameter verweist auf den deklarierten Typ des Members. Dieser Parameter ist der Ersatzzeichentyp, der durch die `GetDataContractType`-Methode zurückgegeben wird. Der- `obj` Parameter verweist auf das Objekt, das deserialisiert wurde. Das Objekt kann zurück in seinen ursprünglichen Typ konvertiert werden, wenn es ersetzt wurde. Diese Methode gibt den Eingabeobjekttyp zurück, wenn das Ersatzzeichen das Objekt nicht behandelt. Andernfalls wird das deserialisierte Objekt zurückgegeben, sobald seine Konvertierung abgeschlossen ist. Wenn verschiedene Ersatzzeichentypen existieren, können Sie für jeden dieser Typen die Datenkonvertierung vom Ersatzzeichentyp in den Primärtyp bewirken, indem Sie jeden Typ und dessen Konvertierung angeben.  
  
 Beim Zurückgeben eines Objekts werden die internen Objekttabellen mit dem von diesem Ersatzzeichen zurückgegebenen Objekt aktualisiert. Alle nachfolgenden Verweise auf eine Instanz rufen die Ersatzzeicheninstanz aus den Objekttabellen ab.  
  
 Im vorherigen Beispiel werden Objekte des Typs `InventorySurrogated` zurück in den ursprünglichen Typ `Inventory` konvertiert. In diesem Fall werden die Daten direkt von `InventorySurrogated` auf seine entsprechenden Felder in `Inventory` zurückübertragen. Da es keine Datenänderungen gibt, enthält jedes der Memberfelder dieselben Werte wie vor der Serialisierung.  
  
### <a name="getcustomdatatoexport-method"></a>GetCustomDataToExport-Methode  

 Beim Exportieren eines Schemas ist die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetCustomDataToExport%2A>-Methode optional. Sie wird verwendet, um zusätzliche Daten oder Hinweise in das exportierte Schema einzufügen. Zusätzliche Daten können auf Memberebene oder auf Typebene eingefügt werden. Beispiel:  
  
 [!code-csharp[C_IDataContractSurrogate#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#6)]  
  
 Diese Methode (mit zwei Überladungen) ermöglicht die Einbeziehung zusätzlicher Informationen in die Metadaten auf der Member- oder der Typebene. Damit ist es möglich, Hinweise dazu einzubeziehen, ob ein Member öffentlich oder privat ist, sowie Kommentare, die während des gesamten Exports und Imports des Schemas beibehalten werden. Solche Informationen würden ohne diese Methode verloren gehen. Diese Methode bewirkt nicht das Einfügen oder Löschen von Membern oder Typen, sondern fügt dem Schema auf diesen beiden Ebenen zusätzliche Daten hinzu.  
  
 Die Methode wird überladen und kann entweder einen `Type` (`clrtype`-Parameter) oder <xref:System.Reflection.MemberInfo> (`memberInfo`-Parameter) nehmen. Der zweite Parameter ist immer ein `Type` (`dataContractType`-Parameter). Diese Methode wird für jeden Member und jeden Typ des ersetzten `dataContractType`-Typs aufgerufen.  
  
 Beide dieser Überladungen müssen entweder `null` oder ein serialisierbares Objekt zurückgeben. Ein Nicht-NULL-Objekt wird als Anmerkung in das exportierte Schema serialisiert. Bei der `Type`-Überladung wird jeder Typ, der in das Schema exportiert wird, im ersten Parameter zusammen mit dem Ersatzzeichentyp als der `dataContractType`-Parameter zu dieser Methode gesendet. Bei der `MemberInfo`-Überladung sendet jeder Member, der in das Schema exportiert wird, seine Informationen als den `memberInfo`-Parameter mit dem Ersatzzeichentyp im zweiten Parameter.  
  
#### <a name="getcustomdatatoexport-method-type-type"></a>GetCustomDataToExport-Methode (Typ, Typ)  

 Die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetCustomDataToExport%28System.Type%2CSystem.Type%29?displayProperty=nameWithType>-Methode wird während des Schemaexports für jede Typdefinition aufgerufen. Die Methode fügt den Typen innerhalb des Schemas beim Export Informationen hinzu. Jeder definierte Typ wird zu dieser Methode gesendet, um zu überprüfen, ob es zusätzliche Daten gibt, die in das Schema einbezogen werden müssen.  
  
#### <a name="getcustomdatatoexport-method-memberinfo-type"></a>GetCustomDataToExport-Methode (MemberInfo, Typ)  

 Die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetCustomDataToExport%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=nameWithType>-Methode wird während des Exports für jeden Member in den Typen aufgerufen, die exportiert werden. Mit dieser Funktion können Sie alle Kommentare für die Member anpassen, die beim Export in das Schema aufgenommen werden. Die Informationen für jeden Member innerhalb der Klasse werden an diese Methode gesendet, um zu überprüfen, ob irgendwelche zusätzlichen Daten zum Schema hinzugefügt werden müssen.  
  
 Das obige Beispiel durchsucht den `dataContractType` für jeden Member des Ersatzzeichens. Es gibt dann den entsprechenden Zugriffsmodifizierer für jedes Feld zurück. Ohne diese Anpassung ist der Standardwert für Zugriffsmodifizierer öffentlich. Deshalb würden alle Member in dem mit dem exportierten Schema generierten Code als öffentlich definiert, und zwar unabhängig davon, welche tatsächlichen Zugriffsbeschränkungen für sie gelten. Wenn diese Implementierung nicht verwendet wird, wäre der Member `numpens` im exportierten Schema öffentlich, obwohl er im Ersatzzeichen als privat definiert wurde. Durch die Verwendung dieser Methode kann der Zugriffsmodifizierer im exportierten Schema als privat generiert werden.  
  
### <a name="getreferencedtypeonimport-method"></a>GetReferencedTypeOnImport-Methode  

 Diese Methode ordnet dem ursprünglichen Typ den <xref:System.Type> des Ersatzzeichens zu. Diese Methode ist für den Import von Schemas optional.  
  
 Beim Erstellen eines Ersatzzeichens, das ein Schema importiert und für dieses Code generiert, besteht die nächste Aufgabe darin, den Typ einer Ersatzzeicheninstanz auf ihren ursprünglichen Typ festzulegen.  
  
 Wenn der generierte Code auf einen existierenden Benutzertyp verweisen muss, wird dies durch die Implementierung der <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%2A>-Methode erreicht.  
  
 Beim Importieren eines Schemas wird diese Methode für jede Typdeklaration aufgerufen, um einem Typ den Ersatzzeichen-Datenvertrag zuzuordnen. Die Zeichenfolgenparameter `typeName` und `typeNamespace` definieren den Namen und den Namespace des Ersatzzeichentyps. Der Rückgabewert für <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%2A> wird verwendet, um zu ermitteln, ob ein neuer Typ generiert werden muss. Diese Methode muss entweder einen gültigen Typ oder NULL zurückgeben. Für gültige Typen wird der zurückgegebene Typ im generierten Code als ein Typ verwendet, auf den verwiesen wird. Wenn NULL zurückgegeben wird, wird auf keinen Typ verwiesen, und ein neuer Typ muss erstellt werden. Wenn mehrere Ersatzzeichen existieren, kann die Zuordnung für jeden Ersatzzeichentyp zurück zu seinem anfänglichen Typ durchgeführt werden.  
  
 Der `customData`-Parameter ist das Objekt, das ursprünglich von <xref:System.Runtime.Serialization.IDataContractSurrogate.GetCustomDataToExport%2A> zurückgegeben wurde. Dieser `customData`-Parameter wird verwendet, wenn Autoren von Ersatzzeichen zusätzliche Daten/Hinweise in die Metadaten einfügen möchten, um sie während des Imports zum Generieren von Code zu verwenden.  
  
### <a name="processimportedtype-method"></a>ProcessImportedType-Methode  

 Die <xref:System.Runtime.Serialization.IDataContractSurrogate.ProcessImportedType%2A>-Methode passt jeden aus dem Schemaimport erstellten Typ an. Diese Methode ist optional.  
  
 Beim Importieren eines Schemas ermöglicht diese Methode die Anpassung jeder importierten Typ- und Kompilierungsinformation. Beispiel:  
  
 [!code-csharp[C_IDataContractSurrogate#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#7)]  
  
 Während des Imports wird diese Methode für jeden generierten Typ aufgerufen. Ändern der angegebenen <xref:System.CodeDom.CodeTypeDeclaration> oder Ändern der <xref:System.CodeDom.CodeCompileUnit>. Dies schließt das Ändern von Namen, Membern, Attributen und vielen anderen Eigenschaften der `CodeTypeDeclaration` ein. Durch Verarbeiten der `CodeCompileUnit` ist es möglich, die Anweisungen, die Namespaces, die referenzierten Assemblys und verschiedene andere Aspekte zu ändern.  
  
 Der `CodeTypeDeclaration`-Parameter enthält die Code-DOM-Typdeklaration. Der `CodeCompileUnit`-Parameter ermöglicht die Änderung zum Verarbeiten des Codes.  Zurückgeben von `null`-Ergebnissen in der Typdeklaration, die verworfen wird. Umgekehrt werden beim Zurückgeben einer `CodeTypeDeclaration` die Änderungen beibehalten.  
  
 Wenn während des Metadatenexports benutzerdefinierte Daten eingefügt werden, müssen diese dem Benutzer beim Import so zur Verfügung gestellt werden, dass sie verwendet werden können. Diese benutzerdefinierten Daten können zur Programmierung von Modellhinweisen oder anderen Kommentaren verwendet werden. Jede `CodeTypeDeclaration`- und <xref:System.CodeDom.CodeTypeMember>-Instanz schließt benutzerdefinierte Daten als die <xref:System.CodeDom.CodeObject.UserData%2A>-Eigenschaft ein, die in den `IDataContractSurrogate`-Typ umgewandelt wird.  
  
 Das obige Beispiel führt einige Änderungen an dem importierten Schema durch. Der Code behält private Member des ursprünglichen Typs bei, indem ein Ersatzzeichen verwendet wird. Der Standardzugriffsmodifizierer beim Importieren eines Schemas ist `public`. Deshalb sind alle Member des Ersatzzeichenschemas öffentlich, es sei denn, es erfolgen Änderungen, wie in diesem Beispiel. Während des Exports werden in die Metadaten benutzerdefinierte Daten darüber eingefügt, welche Member privat sind. Im Beispiel wird nach den benutzerdefinierten Daten gesucht, es wird überprüft, ob der Zugriffsmodifizierer privat ist, und der entsprechende Member wird dann durch Festlegen seiner Attribute zu privat geändert. Ohne diese Anpassung würde der `numpens`-Member nicht als privat, sondern als öffentlich definiert werden.  
  
### <a name="getknowncustomdatatypes-method"></a>GetKnownCustomDataTypes-Methode  

 Diese Methode gewinnt aus dem Schema definierte benutzerdefinierte Datentypen. Die Methode ist für den Import von Schemas optional.  
  
 Die Methode wird zu Beginn des Schemaexports und -imports aufgerufen. Die Methode gibt die benutzerdefinierten Datentypen zurück, die im exportierten oder importierten Schema verwendet werden. An die Methode wird ein <xref:System.Collections.ObjectModel.Collection%601> übergeben (der `customDataTypes`), wobei es sich um eine Sammlung von Typen handelt. Die Methode sollte dieser Sammlung zusätzliche bekannte Typen hinzufügen. Die bekannten benutzerdefinierten Datentypen werden benötigt, um die Serialisierung und Deserialisierung von benutzerdefinierten Daten mit dem <xref:System.Runtime.Serialization.DataContractSerializer> zu ermöglichen. Weitere Informationen finden Sie unter [Data Contract Known Types](../feature-details/data-contract-known-types.md).  
  
## <a name="implementing-a-surrogate"></a>Implementieren eines Ersatzzeichens  

 Um das Datenvertrag-Ersatz Zeichen innerhalb von WCF zu verwenden, müssen Sie einige besondere Prozeduren befolgen.  
  
### <a name="to-use-a-surrogate-for-serialization-and-deserialization"></a>So verwenden Sie ein Ersatzzeichen für die Serialisierung und Deserialisierung  

 Verwenden Sie das <xref:System.Runtime.Serialization.DataContractSerializer>, um die Serialisierung und die Deserialisierung von Daten mit dem Ersatzzeichen durchzuführen. Das <xref:System.Runtime.Serialization.DataContractSerializer> wird durch das <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> erstellt. Das Ersatzzeichen muss ebenfalls angegeben werden.  
  
##### <a name="to-implement-serialization-and-deserialization"></a>So implementieren Sie die Serialisierung und die Deserialisierung  
  
1. Erstellen Sie eine Instanz des <xref:System.ServiceModel.ServiceHost> für Ihren Dienst. Umfassende Anweisungen finden Sie unter [grundlegende WCF-Programmierung](../basic-wcf-programming.md).  
  
2. Suchen Sie für jeden <xref:System.ServiceModel.Description.ServiceEndpoint> des angegebenen Diensthosts seine <xref:System.ServiceModel.Description.OperationDescription>.  
  
3. Durchsuchen Sie die Vorgangsverhalten, um zu ermitteln, ob eine Instanz von <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> gefunden wird.  
  
4. Wenn ein <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> gefunden wird, legen Sie dessen <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.DataContractSurrogate%2A>-Eigenschaft auf eine neue Instanz des Ersatzzeichens fest. Wenn kein <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> gefunden wird, dann erstellen Sie eine neue Instanz, und legen Sie den <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.DataContractSurrogate%2A>-Member des neuen Verhaltens auf eine neue Instanz des Ersatzzeichens fest.  
  
5. Fügen Sie dieses neue Verhalten schließlich den aktuellen Vorgangsverhalten hinzu, wie im folgenden Beispiel gezeigt wird:  
  
     [!code-csharp[C_IDataContractSurrogate#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#8)]  
  
### <a name="to-use-a-surrogate-for-metadata-import"></a>So verwenden Sie ein Ersatzzeichen für den Metadatenimport  

 Beim Importieren von Metadaten wie WSDL und XSD zum Generieren von clientseitigem Code muss das Ersatzzeichen zur Komponente <xref:System.Runtime.Serialization.XsdDataContractImporter>, die für das Generieren von Code aus dem XSD-Schema verantwortlich ist, hinzugefügt werden. Dazu ändern Sie direkt den zum Importieren von Metadaten verwendeten <xref:System.ServiceModel.Description.WsdlImporter>.  
  
##### <a name="to-implement-a-surrogate-for-metadata-importation"></a>So implementieren Sie ein Ersatzzeichen für den Metadatenimport  
  
1. Importieren Sie die Metadaten mit der <xref:System.ServiceModel.Description.WsdlImporter>-Klasse.  
  
2. Verwenden Sie die <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>-Methode zur Überprüfung, ob ein <xref:System.Runtime.Serialization.XsdDataContractImporter> definiert wurde.  
  
3. Wenn die <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>-Methode `false` zurückgibt, erstellen Sie einen neuen <xref:System.Runtime.Serialization.XsdDataContractImporter>, und legen Sie dessen <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A>-Eigenschaft auf eine neue Instanz der <xref:System.Runtime.Serialization.ImportOptions>-Klasse fest. Verwenden Sie andernfalls den durch den `out`-Parameter der <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>-Methode zurückgegebenen Importer.  
  
4. Wenn für den <xref:System.Runtime.Serialization.XsdDataContractImporter> keine <xref:System.Runtime.Serialization.ImportOptions> definiert sind, dann legen Sie die Eigenschaft auf eine neue Instanz der <xref:System.Runtime.Serialization.ImportOptions>-Klasse fest.  
  
5. Legen Sie die <xref:System.Runtime.Serialization.ImportOptions.DataContractSurrogate%2A>-Eigenschaft der <xref:System.Runtime.Serialization.ImportOptions> des <xref:System.Runtime.Serialization.XsdDataContractImporter> auf eine neue Instanz des Ersatzzeichens fest.  
  
6. Fügen Sie den <xref:System.Runtime.Serialization.XsdDataContractImporter> der Sammlung hinzu, die durch die <xref:System.ServiceModel.Description.MetadataExporter.State%2A>-Eigenschaft des <xref:System.ServiceModel.Description.WsdlImporter> (geerbt von der <xref:System.ServiceModel.Description.MetadataExporter>-Klasse) zurückgegeben wird.  
  
7. Verwenden Sie die <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>-Methode des <xref:System.ServiceModel.Description.WsdlImporter> zum Importieren sämtlicher Datenverträge innerhalb des Schemas. Während des letzten Schritts wird Code aus den geladenen Schemas durch Aufruf in das Ersatzzeichen generiert.  
  
     [!code-csharp[C_IDataContractSurrogate#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#9)]  
  
### <a name="to-use-a-surrogate-for-metadata-export"></a>So verwenden Sie ein Ersatzzeichen für den Metadatenexport  

 Beim Exportieren von Metadaten aus WCF für einen Dienst müssen standardmäßig sowohl das WSDL-als auch das XSD-Schema generiert werden. Das Ersatzzeichen muss der Komponente <xref:System.Runtime.Serialization.XsdDataContractExporter> hinzugefügt werden, die für das Generieren des XSD-Schemas für Datenvertragstypen verantwortlich ist. Dazu verwenden Sie entweder ein Verhalten, das <xref:System.ServiceModel.Description.IWsdlExportExtension> implementiert, um das <xref:System.ServiceModel.Description.WsdlExporter> zu ändern, oder ändern Sie das zum Exportieren von Metadaten verwendete <xref:System.ServiceModel.Description.WsdlExporter> direkt.  
  
##### <a name="to-use-a-surrogate-for-metadata-export"></a>So verwenden Sie ein Ersatzzeichen für den Metadatenexport  
  
1. Erstellen Sie ein neues <xref:System.ServiceModel.Description.WsdlExporter>, oder verwenden Sie den `wsdlExporter`-Parameter, der an die <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A>-Methode übergeben wird.  
  
2. Verwenden Sie die <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>-Funktion zur Überprüfung, ob ein <xref:System.Runtime.Serialization.XsdDataContractExporter> definiert wurde.  
  
3. Wenn <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>`false` zurückgibt, erstellen Sie ein neues <xref:System.Runtime.Serialization.XsdDataContractExporter> mit den generierten XML-Schemas aus dem <xref:System.ServiceModel.Description.WsdlExporter>, und fügen Sie diesen der Sammlung hinzu, die durch die <xref:System.ServiceModel.Description.MetadataExporter.State%2A>-Eigenschaft des <xref:System.ServiceModel.Description.WsdlExporter> zurückgegeben wird. Verwenden Sie andernfalls das Exportprogramm, das durch den `out`-Parameter der <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>-Methode zurückgegeben wird.  
  
4. Wenn für das <xref:System.Runtime.Serialization.XsdDataContractExporter> keine <xref:System.Runtime.Serialization.ExportOptions> definiert sind, dann legen Sie die <xref:System.Runtime.Serialization.XsdDataContractExporter.Options%2A>-Eigenschaft auf eine neue Instanz der <xref:System.Runtime.Serialization.ExportOptions>-Klasse fest.  
  
5. Legen Sie die <xref:System.Runtime.Serialization.ExportOptions.DataContractSurrogate%2A>-Eigenschaft der <xref:System.Runtime.Serialization.ExportOptions> des <xref:System.Runtime.Serialization.XsdDataContractExporter> auf eine neue Instanz des Ersatzzeichens fest. Die nachfolgenden Schritte zum Exportieren von Metadaten erfordern keine Änderungen.  
  
     [!code-csharp[C_IDataContractSurrogate#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#10)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.IDataContractSurrogate>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.Runtime.Serialization.ImportOptions>
- <xref:System.Runtime.Serialization.ExportOptions>
- [Verwenden von Datenverträgen](../feature-details/using-data-contracts.md)
