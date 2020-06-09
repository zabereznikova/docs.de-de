---
title: DataContract-Ersatzzeichen
ms.date: 03/30/2017
ms.assetid: b0188f3c-00a9-4cf0-a887-a2284c8fb014
ms.openlocfilehash: 9677e3cf024e6c1e5b2f3360423ab55536748495
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600035"
---
# <a name="datacontract-surrogate"></a>DataContract-Ersatzzeichen
In diesem Beispiel wird beschrieben, wie Vorgänge wie Serialisierung, Deserialisierung, Schemaexport und Schemaimport mithilfe einer Datenvertrag-Ersatzzeichenklasse angepasst werden können. In diesem Beispiel wird gezeigt, wie ein Ersatz Zeichen in einem Client-und Server Szenario verwendet wird, in dem Daten zwischen einem Windows Communication Foundation (WCF)-Client und-Dienst serialisiert und übertragen werden.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Im Beispiel wird der folgende Dienstvertrag verwendet.  
  
```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
[AllowNonSerializableTypes]  
public interface IPersonnelDataService  
{  
    [OperationContract]  
    void AddEmployee(Employee employee);  
  
    [OperationContract]  
    Employee GetEmployee(string name);  
}  
```  
  
 Mit dem `AddEmployee`-Vorgang können Benutzer Daten zu neuen Mitarbeitern hinzufügen. Der `GetEmployee`-Vorgang unterstützt das Suchen von Mitarbeitern nach Namen.  
  
 In diesen Vorgängen wird der folgende Datentyp verwendet:  
  
```csharp
[DataContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
class Employee  
{  
    [DataMember]  
    public DateTime dateHired;  
  
    [DataMember]  
    public Decimal salary;  
  
    [DataMember]  
    public Person person;  
}  
```  
  
 Im `Employee`-Typ kann die `Person`-Klasse (im folgenden Beispielcode dargestellt) nicht von <xref:System.Runtime.Serialization.DataContractSerializer> serialisiert werden, da es sich nicht um eine gültige Datenvertragsklasse handelt.  
  
```csharp
public class Person  
{  
    public string firstName;  
  
    public string lastName;  
  
    public int age;  
  
    public Person() { }  
}  
```  
  
 Sie können das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf die `Person`-Klasse anwenden, dies ist jedoch nicht immer möglich. Die `Person`-Klasse kann beispielsweise in einer separaten Assembly definiert sein, auf die Sie keinen Einfluss haben.  
  
 Wenn diese Einschränkung vorliegt, besteht eine Möglichkeit zum Serialisieren der `Person`-Klasse darin, sie durch eine andere Klasse zu ersetzen, die mit <xref:System.Runtime.Serialization.DataContractAttribute> markiert ist, und erforderliche Daten in die neue Klasse zu kopieren. Das Ziel ist dabei, die `Person`-Klasse für <xref:System.Runtime.Serialization.DataContractSerializer> als DataContract erscheinen zu lassen. Beachten Sie, dass dies eine Möglichkeit zum Serialisieren von Klassen ist, bei denen es sich nicht um Datenvertragsklassen handelt.  
  
 Im Beispiel wird die `Person`-Klasse logisch durch eine andere Klasse namens `PersonSurrogated` ersetzt.  
  
```csharp
[DataContract(Name="Person", Namespace = "http://Microsoft.ServiceModel.Samples")]  
public class PersonSurrogated  
{  
    [DataMember]  
    public string FirstName;  
  
    [DataMember]  
    public string LastName;  
  
    [DataMember]  
    public int Age;  
}  
```  
  
 Zum Durchführen dieser Ersetzung wird das Datenvertrag-Ersatzzeichen verwendet. Ein Datenvertrag-Ersatzzeichen ist eine Klasse, die <xref:System.Runtime.Serialization.IDataContractSurrogate> implementiert. In diesem Beispiel implementiert die `AllowNonSerializableTypesSurrogate`-Klasse diese Schnittstelle.  
  
 In der Schnittstellenimplementierung ist die erste Aufgabe das Einrichten einer Typzuordnung von `Person` zu `PersonSurrogated`. Dies wird bei der Serialisierung sowie beim Schemaexport verwendet. Diese Zuordnung erfolgt durch das Implementieren der <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%28System.Type%29>-Methode.  
  
```csharp
public Type GetDataContractType(Type type)  
{  
    if (typeof(Person).IsAssignableFrom(type))  
    {  
        return typeof(PersonSurrogated);  
    }  
    return type;  
}  
```  
  
 Die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%28System.Object%2CSystem.Type%29>-Methode ordnet bei der Serialisierung eine `Person`-Instanz einer `PersonSurrogated`-Instanz zu, wie im folgenden Beispielcode dargestellt.  
  
```csharp
public object GetObjectToSerialize(object obj, Type targetType)  
{  
    if (obj is Person)  
    {  
        Person person = (Person)obj;  
        PersonSurrogated personSurrogated = new PersonSurrogated();  
        personSurrogated.FirstName = person.firstName;  
        personSurrogated.LastName = person.lastName;  
        personSurrogated.Age = person.age;  
        return personSurrogated;  
    }  
    return obj;  
}  
```  
  
 Die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%28System.Object%2CSystem.Type%29>-Methode stellt die umgekehrte Zuordnung für die Deserialisierung bereit, wie im folgenden Beispielcode gezeigt.  
  
```csharp
public object GetDeserializedObject(object obj,
Type targetType)  
{  
    if (obj is PersonSurrogated)  
    {  
        PersonSurrogated personSurrogated = (PersonSurrogated)obj;  
        Person person = new Person();  
        person.firstName = personSurrogated.FirstName;  
        person.lastName = personSurrogated.LastName;  
        person.age = personSurrogated.Age;  
        return person;  
    }  
    return obj;  
}  
```  
  
 Zum Zuordnen des `PersonSurrogated`-Datenvertrags zu der vorhandenen `Person`-Klasse beim Schemaimport wird im Beispiel die <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%28System.String%2CSystem.String%2CSystem.Object%29>-Methode implementiert, wie im folgenden Beispielcode veranschaulicht.  
  
```csharp
public Type GetReferencedTypeOnImport(string typeName,
               string typeNamespace, object customData)  
{  
if (  
typeNamespace.Equals("http://schemas.datacontract.org/2004/07/DCSurrogateSample")  
)  
    {  
         if (typeName.Equals("PersonSurrogated"))  
        {  
             return typeof(Person);  
        }  
     }  
     return null;  
}  
```  
  
 Im folgenden Beispielcode wird die Implementierung der <xref:System.Runtime.Serialization.IDataContractSurrogate>-Schnittstelle abgeschlossen.  
  
```csharp
public System.CodeDom.CodeTypeDeclaration ProcessImportedType(  
          System.CodeDom.CodeTypeDeclaration typeDeclaration,
          System.CodeDom.CodeCompileUnit compileUnit)  
{  
    return typeDeclaration;  
}  
public object GetCustomDataToExport(Type clrType,
                               Type dataContractType)  
{  
    return null;  
}  
  
public object GetCustomDataToExport(  
System.Reflection.MemberInfo memberInfo, Type dataContractType)  
{  
    return null;  
}  
public void GetKnownCustomDataTypes(  
        KnownTypeCollection customDataTypes)  
{  
    // It does not matter what we do here.  
    throw new NotImplementedException();  
}  
```  
  
 In diesem Beispiel wird das Ersatzzeichen in ServiceModel von dem Attribut `AllowNonSerializableTypesAttribute` aktiviert. Entwickler müssten dieses Attribut auf ihren Dienstvertrag anwenden, wie oben im `IPersonnelDataService`-Dienstvertrag dargestellt. Dieses Attribut implementiert `IContractBehavior` und richtet das Ersatzzeichen bei Vorgängen in der `ApplyClientBehavior`-Methode und der `ApplyDispatchBehavior`-Methode ein.  
  
 Das Attribut ist in diesem Fall nicht erforderlich. Es wird in diesem Beispiel nur zur Veranschaulichung verwendet. Die Benutzer können ein Ersatzzeichen auch aktivieren, indem sie mithilfe von Code oder Konfiguration ein ähnliches `IContractBehavior`, `IEndpointBehavior` oder `IOperationBehavior` hinzufügen.  
  
 Die `IContractBehavior`-Implementierung sucht nach Vorgängen, die DataContract verwenden, indem überprüft wird, ob `DataContractSerializerOperationBehavior` registriert ist. Wenn dies der Fall ist, wird die `DataContractSurrogate`-Eigenschaft auf dieses Verhalten festgelegt. Der folgende Beispielcode zeigt die Vorgehensweise. Durch das Festlegen des Ersatzzeichens auf dieses Vorgangsverhalten wird es für die Serialisierung und die Deserialisierung aktiviert.  
  
```csharp
public void ApplyClientBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime proxy)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
public void ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatch)  
{  
    foreach (OperationDescription opDesc in description.Operations)  
    {  
        ApplyDataContractSurrogate(opDesc);  
    }  
}  
  
private static void ApplyDataContractSurrogate(OperationDescription description)  
{  
    DataContractSerializerOperationBehavior dcsOperationBehavior = description.Behaviors.Find<DataContractSerializerOperationBehavior>();  
    if (dcsOperationBehavior != null)  
    {  
        if (dcsOperationBehavior.DataContractSurrogate == null)  
            dcsOperationBehavior.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
    }  
}  
```  
  
 Damit das Ersatzzeichen für die Verwendung bei der Metadaten-Generierung eingebunden werden kann, sind zusätzliche Schritte erforderlich. Ein Mechanismus hierfür ist das Bereitstellen einer `IWsdlExportExtension`. Dies wird in diesem Beispiel veranschaulicht. Eine andere Möglichkeit ist das direkte Ändern von `WsdlExporter`.  
  
 Das `AllowNonSerializableTypesAttribute` Attribut implementiert `IWsdlExportExtension` und `IContractBehavior` . Die Erweiterung kann `IContractBehavior` `IEndpointBehavior` in diesem Fall entweder oder sein. Die Implementierung der `IWsdlExportExtension.ExportContract`-Methode aktiviert das Ersatzzeichen, indem es dem bei der Schemagenerierung für DataContract verwendeten `XsdDataContractExporter` hinzugefügt wird. Der folgende Codeausschnitt veranschaulicht, wie Sie dabei vorgehen müssen:  
  
```csharp
public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)  
{  
    if (exporter == null)  
        throw new ArgumentNullException("exporter");  
  
    object dataContractExporter;  
    XsdDataContractExporter xsdDCExporter;  
    if (!exporter.State.TryGetValue(typeof(XsdDataContractExporter), out dataContractExporter))  
    {  
        xsdDCExporter = new XsdDataContractExporter(exporter.GeneratedXmlSchemas);  
        exporter.State.Add(typeof(XsdDataContractExporter), xsdDCExporter);  
    }  
    else  
    {  
        xsdDCExporter = (XsdDataContractExporter)dataContractExporter;  
    }  
    if (xsdDCExporter.Options == null)  
        xsdDCExporter.Options = new ExportOptions();  
  
    if (xsdDCExporter.Options.DataContractSurrogate == null)  
        xsdDCExporter.Options.DataContractSurrogate = new AllowNonSerializableTypesSurrogate();  
}  
```  
  
 Wenn Sie das Beispiel ausführen, ruft der Client AddEmployee auf. Danach folgt ein Aufruf von GetEmployee, um zu überprüfen, ob der erste Aufruf erfolgreich war. Das Ergebnis der GetEmployee-Vorgangsanforderung wird im Clientkonsolenfenster angezeigt. Der GetEmployee-Vorgang muss bei der Suche nach dem Mitarbeiter erfolgreich sein und "found" Drucken.  
  
> [!NOTE]
> In diesem Beispiel wird das Einbinden eines Ersatzzeichens zum Serialisieren, Deserialisieren und für die Metadatengenerierung veranschaulicht. Das Einbinden eines Ersatzzeichens für die Codegenerierung aus Metadaten wird nicht dargestellt. Ein Beispiel für die Verwendung eines Ersatz Zeichens zum Einbinden der Client Codegenerierung finden Sie im Beispiel für eine [benutzerdefinierte WSDL-Veröffentlichung](custom-wsdl-publication.md) .  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die c#-Edition der Projekt Mappe zu erstellen, befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation Beispiele](building-the-samples.md).  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DataContract`  
