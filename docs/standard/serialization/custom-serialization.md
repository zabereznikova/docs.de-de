---
title: Benutzerdefinierte Serialisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binary serialization, custom serialization
- custom serialization
- binary serialization, controlling
- OptionalFieldAttribute class, custom serialization
- ISerializable interface, custom serialization
- OnDeserializingAttribute class, custom serialization
- OnSerializedAttribute class, custom serialization
- serialization, custom serialization
- serialization, controlling
- OnDeserializedAttribute class, custom serialization
- OnSerializingAttribute class, custom serialization
ms.assetid: 12ed422d-5280-49b8-9b71-a2ed129c0384
ms.openlocfilehash: 60fdc0317975d94433401e3214953b77d0970f60
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741056"
---
# <a name="custom-serialization"></a><span data-ttu-id="6a6af-102">Benutzerdefinierte Serialisierung</span><span class="sxs-lookup"><span data-stu-id="6a6af-102">Custom serialization</span></span>
<span data-ttu-id="6a6af-103">Unter benutzerdefinierter Serialisierung wird die Steuerung der Serialisierung und Deserialisierung eines Typs verstanden.</span><span class="sxs-lookup"><span data-stu-id="6a6af-103">Custom serialization is the process of controlling the serialization and deserialization of a type.</span></span> <span data-ttu-id="6a6af-104">Durch die Steuerung der Serialisierung lässt sich die Serialisierungskompatibilität sicherstellen. Damit ist die Fähigkeit gemeint, Objekte unterschiedlicher Versionen eines Typs serialisieren und deserialisieren zu können, ohne die Kernfunktionalität des Typs zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-104">By controlling serialization, it's possible to ensure serialization compatibility, which is the ability to serialize and deserialize between versions of a type without breaking the core functionality of the type.</span></span> <span data-ttu-id="6a6af-105">Zum Beispiel kann die erste Version eines Typs nur zwei Felder umfassen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-105">For example, in the first version of a type, there may be only two fields.</span></span> <span data-ttu-id="6a6af-106">In der nächsten Version des Typs werden mehrere weitere Felder hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6a6af-106">In the next version of a type, several more fields are added.</span></span> <span data-ttu-id="6a6af-107">Die zweite Version einer Anwendung muss jedoch fähig sein, beide Typen zu serialisieren und zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="6a6af-107">Yet the second version of an application must be able to serialize and deserialize both types.</span></span> <span data-ttu-id="6a6af-108">In den folgenden Abschnitten wird beschrieben, wie Serialisierung gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="6a6af-108">The following sections describe how to control serialization.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
> [!IMPORTANT]
> <span data-ttu-id="6a6af-109">In Versionen vor .NET Framework 4.0 wurde die Serialisierung benutzerdefinierter Benutzerdaten in einer teilweise vertrauenswürdigen Assembly mit GetObjectData erreicht.</span><span class="sxs-lookup"><span data-stu-id="6a6af-109">In versions previous to .NET Framework 4.0, serialization of custom user data in a partially trusted assembly was accomplished using the GetObjectData.</span></span> <span data-ttu-id="6a6af-110">Ab Version 4 wird diese Methode mit dem <xref:System.Security.SecurityCriticalAttribute>-Attribut markiert, das die Ausführung in teilweise vertrauenswürdigen Assemblys verhindert.</span><span class="sxs-lookup"><span data-stu-id="6a6af-110">Starting with version 4.0, that method is marked with the <xref:System.Security.SecurityCriticalAttribute> attribute which prevents execution in partially trusted assemblies.</span></span> <span data-ttu-id="6a6af-111">Um diese Bedingung zu umgehen, implementieren Sie die <xref:System.Runtime.Serialization.ISafeSerializationData>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6a6af-111">To work around this condition, implement the <xref:System.Runtime.Serialization.ISafeSerializationData> interface.</span></span>  
  
## <a name="running-custom-methods-during-and-after-serialization"></a><span data-ttu-id="6a6af-112">Ausführen von benutzerdefinierten Methoden während und nach der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="6a6af-112">Running custom methods during and after serialization</span></span>  
 <span data-ttu-id="6a6af-113">Die empfohlene und einfachste Vorgehensweise (eingeführt in Version&#160;2.0 von .NET&#160;Framework) ist es, die folgenden Attribute für Methoden zu verwenden, die zum Korrigieren von Daten während und nach der Serialisierung verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="6a6af-113">The best practice and easiest way (introduced in version 2.0 of the .NET Framework) is to apply the following attributes to methods that are used to correct data during and after serialization:</span></span>  
  
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
- <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
 <span data-ttu-id="6a6af-114">Diese Attribute ermöglichen es dem Typ, an jeder einzelnen Phase bzw. an allen vier Phasen des Serialisierungs- und Deserialisierungsprozesses teilzuhaben.</span><span class="sxs-lookup"><span data-stu-id="6a6af-114">These attributes allow the type to participate in any one of, or all four of the phases, of the serialization and deserialization processes.</span></span> <span data-ttu-id="6a6af-115">Die Attribute geben die Methoden des Typs an, die während jeder Phase aufgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-115">The attributes specify the methods of the type that should be invoked during each phase.</span></span> <span data-ttu-id="6a6af-116">Die Methoden greifen nicht auf den Serialisierungsstream zu, sondern ermöglichen es Ihnen, das Objekt vor und nach der Serialisierung bzw. vor oder nach der Deserialisierung zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6a6af-116">The methods do not access the serialization stream but instead allow you to alter the object before and after serialization, or before and after deserialization.</span></span> <span data-ttu-id="6a6af-117">Die Attribute können auf allen Vererbungshierarchieebenen des Typs verwendet werden. Jede Methode wird in der Hierarchie von der Basis zur am weitesten abgeleiteten Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-117">The attributes can be applied at all levels of the type inheritance hierarchy, and each method is called in the hierarchy from the base to the most derived.</span></span> <span data-ttu-id="6a6af-118">Durch diesen Mechanismus werden die Komplexität und alle hieraus entstehenden Probleme bei der Implementierung der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle vermieden, indem die Verantwortung für die Serialisierung und Deserialisierung der am weitesten abgeleiteten Implementierung übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="6a6af-118">This mechanism avoids the complexity and any resulting issues of implementing the <xref:System.Runtime.Serialization.ISerializable> interface by giving the responsibility for serialization and deserialization to the most derived implementation.</span></span> <span data-ttu-id="6a6af-119">Zusätzlich ermöglicht dieser Mechanismus den Formatierungsprogrammen, das Auffüllen von Feldern und das Abrufen von Daten aus dem Serialisierungsstream zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="6a6af-119">Additionally, this mechanism allows the formatters to ignore the population of fields and retrieval from the serialization stream.</span></span> <span data-ttu-id="6a6af-120">Weitere Informationen und Beispiele zum Steuern der Serialisierung und Deserialisierung erhalten Sie, indem Sie auf einen der oben genannten Links klicken.</span><span class="sxs-lookup"><span data-stu-id="6a6af-120">For details and examples of controlling serialization and deserialization, click any of the previous links.</span></span>  
  
 <span data-ttu-id="6a6af-121">Wenn Sie einem bestehenden serialisierbaren Typ ein neues Feld hinzufügen, wenden Sie außerdem das <xref:System.Runtime.Serialization.OptionalFieldAttribute>-Attribut auf das Feld an.</span><span class="sxs-lookup"><span data-stu-id="6a6af-121">In addition, when adding a new field to an existing serializable type, apply the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute to the field.</span></span> <span data-ttu-id="6a6af-122"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> und <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> ignorieren das Fehlen des Felds, wenn ein Stream mit fehlendem neuen Feld verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="6a6af-122">The <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> ignores the absence of the field when a stream that is missing the new field is processed.</span></span>  
  
## <a name="implementing-the-iserializable-interface"></a><span data-ttu-id="6a6af-123">Implementieren der ISerializable-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a6af-123">Implementing the ISerializable interface</span></span>  
 <span data-ttu-id="6a6af-124">Die andere Möglichkeit zum Steuern der Serialisierung besteht in der Implementierung der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle für ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="6a6af-124">The other way to control serialization is achieved by implementing the <xref:System.Runtime.Serialization.ISerializable> interface on an object.</span></span> <span data-ttu-id="6a6af-125">Beachten Sie jedoch, dass die Methode im vorhergehenden Abschnitt beim Steuern der Serialisierung Vorrang vor dieser Methode hat.</span><span class="sxs-lookup"><span data-stu-id="6a6af-125">Note, however, that the method in the previous section supersedes this method to control serialization.</span></span>  
  
 <span data-ttu-id="6a6af-126">Außerdem dürfen Sie keine Standardserialisierung bei einer Klasse verwenden, die mit dem [Serializable](xref:System.SerializableAttribute)-Attribut markiert ist und für die auf Klassenebene oder für ihre Konstruktoren deklarative oder imperative Sicherheit gilt.</span><span class="sxs-lookup"><span data-stu-id="6a6af-126">In addition, you should not use default serialization on a class that is marked with the [Serializable](xref:System.SerializableAttribute) attribute and has declarative or imperative security at the class level or on its constructors.</span></span> <span data-ttu-id="6a6af-127">Stattdessen sollten diese Klassen immer die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="6a6af-127">Instead, these classes should always implement the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>  
  
 <span data-ttu-id="6a6af-128">Die Implementierung von <xref:System.Runtime.Serialization.ISerializable> umfasst auch die Implementierung der `GetObjectData`-Methode und eines speziellen Konstruktors, der bei der Deserialisierung des Objekts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6a6af-128">Implementing <xref:System.Runtime.Serialization.ISerializable> involves implementing the `GetObjectData` method and a special constructor that is used when the object is deserialized.</span></span> <span data-ttu-id="6a6af-129">Der folgende Beispielcode zeigt, wie <xref:System.Runtime.Serialization.ISerializable> für die `MyObject`-Klasse aus einem vorherigen Abschnitt implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="6a6af-129">The following sample code shows how to implement <xref:System.Runtime.Serialization.ISerializable> on the `MyObject` class from a previous section.</span></span>  
  
```csharp
[Serializable]
public class MyObject : ISerializable
{
    public int n1;
    public int n2;
    public String str;

    public MyObject()
    {
    }

    protected MyObject(SerializationInfo info, StreamingContext context)
    {
      n1 = info.GetInt32("i");
      n2 = info.GetInt32("j");
      str = info.GetString("k");
    }

    [SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter = true)]
    public virtual void GetObjectData(SerializationInfo info, StreamingContext context)
    {
        info.AddValue("i", n1);
        info.AddValue("j", n2);
        info.AddValue("k", str);
    }
}
```

```vb
<Serializable()>  _
Public Class MyObject
    Implements ISerializable
    Public n1 As Integer
    Public n2 As Integer
    Public str As String

    Public Sub New()
    End Sub

    Protected Sub New(ByVal info As SerializationInfo, ByVal context As StreamingContext)
        n1 = info.GetInt32("i")
        n2 = info.GetInt32("j")
        str = info.GetString("k")
    End Sub 'New

    <SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)> _
    Public Overridable Sub GetObjectData(ByVal info As SerializationInfo, ByVal context As StreamingContext)
        info.AddValue("i", n1)
        info.AddValue("j", n2)
        info.AddValue("k", str)
    End Sub
End Class
```  
  
 <span data-ttu-id="6a6af-130">Wenn **GetObjectData** während der Serialisierung aufgerufen wird, müssen Sie das mit dem Methodenaufruf bereitgestellte <xref:System.Runtime.Serialization.SerializationInfo> auffüllen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-130">When **GetObjectData** is called during serialization, you are responsible for populating the <xref:System.Runtime.Serialization.SerializationInfo> provided with the method call.</span></span> <span data-ttu-id="6a6af-131">Fügen Sie die zu serialisierenden Variablen einfach als Name/Wert-Paar hinzu.</span><span class="sxs-lookup"><span data-stu-id="6a6af-131">Add the variables to be serialized as name and value pairs.</span></span> <span data-ttu-id="6a6af-132">Beliebiger Text kann als Name verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6a6af-132">Any text can be used as the name.</span></span> <span data-ttu-id="6a6af-133">Sie können frei entscheiden, welche Membervariablen <xref:System.Runtime.Serialization.SerializationInfo> hinzugefügt werden. Voraussetzung ist jedoch, dass genügend Daten serialisiert werden, um das Objekt während der Deserialisierung wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-133">You have the freedom to decide which member variables are added to the <xref:System.Runtime.Serialization.SerializationInfo>, provided that sufficient data is serialized to restore the object during deserialization.</span></span> <span data-ttu-id="6a6af-134">Abgeleitete Klassen sollten die **GetObjectData**-Methode für das Basisobjekt aufrufen, wenn dieses <xref:System.Runtime.Serialization.ISerializable> implementiert.</span><span class="sxs-lookup"><span data-stu-id="6a6af-134">Derived classes should call the **GetObjectData** method on the base object if the latter implements <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
 <span data-ttu-id="6a6af-135">Beachten Sie, dass es durch die Serialisierung anderem Code ermöglicht werden kann, Objektinstanzdaten anzuzeigen oder zu ändern, auf die andernfalls nicht zugegriffen werden .</span><span class="sxs-lookup"><span data-stu-id="6a6af-135">Note that serialization can allow other code to see or modify object instance data that is otherwise inaccessible.</span></span> <span data-ttu-id="6a6af-136">Daher ist für Code, der eine Serialisierung ausführt, [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) unter Angabe des <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter>-Flags erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6a6af-136">Therefore, code that performs serialization requires the [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) with the <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> flag specified.</span></span> <span data-ttu-id="6a6af-137">Entsprechend der Standardrichtlinie bedeutet dies, dass diese Berechtigung nicht für aus dem Internet heruntergeladenen Code oder Code aus einem Intranet erteilt wird. Diese Berechtigung wird nur für Code auf dem lokalen Computer erteilt.</span><span class="sxs-lookup"><span data-stu-id="6a6af-137">Under default policy, this permission is not given to Internet-downloaded or intranet code; only code on the local computer is granted this permission.</span></span> <span data-ttu-id="6a6af-138">Die **GetObjectData**-Methode muss entweder durch Anfordern von [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) unter Angabe des <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter>-Flags oder durch Anfordern von anderen Berechtigungen, die insbesondere private Daten schützen, explizit geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="6a6af-138">The **GetObjectData** method must be explicitly protected either by demanding the [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) with the <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> flag specified or by demanding other permissions that specifically help protect private data.</span></span>  
  
 <span data-ttu-id="6a6af-139">Wenn in einem privaten Feld vertrauliche Informationen gespeichert werden, sollten Sie die entsprechenden Berechtigungen für **GetObjectData** anfordern, um die Daten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-139">If a private field stores sensitive information, you should demand the appropriate permissions on **GetObjectData** to protect the data.</span></span> <span data-ttu-id="6a6af-140">Berücksichtigen Sie, dass ein Code, dem die Berechtigung [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) unter Angabe des **SerializationFormatter**-Flags erteilt wurde, die in privaten Feldern gespeicherten Daten anzeigen und verändern kann.</span><span class="sxs-lookup"><span data-stu-id="6a6af-140">Remember that code that has been granted [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) with the **SerializationFormatter** flag specified can view and modify the data stored in private fields.</span></span> <span data-ttu-id="6a6af-141">Ein böswilliger Aufrufer, dem die Berechtigung [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) erteilt wurde, kann Daten, wie etwa ausgeblendete Verzeichnispfade oder erteilte Berechtigungen, anzeigen und die Daten verwenden, um eine Sicherheitslücke auf dem Computer auszunutzen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-141">A malicious caller granted this [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) can view data such as hidden directory locations or granted permissions and use the data to exploit a security vulnerability on the computer.</span></span> <span data-ttu-id="6a6af-142">Eine vollständige Liste der Flags für Sicherheitsberechtigungen, die Sie angeben können, finden Sie unter [SecurityPermissionFlag-Enumeration](xref:System.Security.Permissions.SecurityPermissionFlag).</span><span class="sxs-lookup"><span data-stu-id="6a6af-142">For a complete list of the security permission flags you can specify, see the [SecurityPermissionFlag Enumeration](xref:System.Security.Permissions.SecurityPermissionFlag).</span></span>  
  
 <span data-ttu-id="6a6af-143">Beachten Sie, dass in einer Klasse, der <xref:System.Runtime.Serialization.ISerializable> hinzugefügt wurde, sowohl **GetObjectData** als auch der spezielle Konstruktor implementiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-143">It's important to stress that when <xref:System.Runtime.Serialization.ISerializable> is added to a class you must implement both **GetObjectData** and the special constructor.</span></span> <span data-ttu-id="6a6af-144">Der Compiler gibt eine Warnung aus, wenn **GetObjectData** fehlt.</span><span class="sxs-lookup"><span data-stu-id="6a6af-144">The compiler warns you if **GetObjectData** is missing.</span></span> <span data-ttu-id="6a6af-145">Wenn jedoch der Konstruktor fehlt, wird keine Warnung ausgegeben, da die Implementierung eines Konstruktors nicht erzwungen werden kann. Wenn außerdem versucht wird, eine Klasse ohne den Konstruktor zu deserialisieren, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6a6af-145">However, because it is impossible to enforce the implementation of a constructor, no warning is provided if the constructor is absent, and an exception is thrown when an attempt is made to deserialize a class without the constructor.</span></span>  
  
 <span data-ttu-id="6a6af-146">Der aktuelle Entwurf wurde einer <xref:System.Runtime.Serialization.ISerializationSurrogate.SetObjectData%2A>-Methode vorgezogen, um potenzielle Sicherheits- und Versionsprobleme zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-146">The current design was favored above a <xref:System.Runtime.Serialization.ISerializationSurrogate.SetObjectData%2A> method to get around potential security and versioning problems.</span></span> <span data-ttu-id="6a6af-147">Eine `SetObjectData`-Methode muss beispielsweise öffentlich sein, wenn sie als Teil einer Schnittstelle definiert wird. Die Benutzer müssen demnach einen Code schreiben, um zu verhindern, dass die **SetObjectData**-Methode mehrfach aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="6a6af-147">For example, a `SetObjectData` method must be public if it is defined as part of an interface; thus users must write code to defend against having the **SetObjectData** method called multiple times.</span></span> <span data-ttu-id="6a6af-148">Andernfalls kann eine bösartige Anwendung, die die **SetObjectData**-Methode für ein Objekt während der Ausführung eines Vorgangs aufruft, Probleme verursachen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-148">Otherwise, a malicious application that calls the **SetObjectData** method on an object in the process of executing an operation can cause potential problems.</span></span>  
  
 <span data-ttu-id="6a6af-149">Während der Deserialisierung wird <xref:System.Runtime.Serialization.SerializationInfo> an die Klasse übergeben, die den für diesen Zweck bereitgestellten Konstruktor verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a6af-149">During deserialization, <xref:System.Runtime.Serialization.SerializationInfo> is passed to the class using the constructor provided for this purpose.</span></span> <span data-ttu-id="6a6af-150">Die für den Konstruktor geltenden Sichtbarkeitseinschränkungen werden bei der Deserialisierung des Objekts ignoriert, d.&#160;h., Sie können die Klasse als öffentlich, geschützt, intern oder privat markieren.</span><span class="sxs-lookup"><span data-stu-id="6a6af-150">Any visibility constraints placed on the constructor are ignored when the object is deserialized; so you can mark the class as public, protected, internal, or private.</span></span> <span data-ttu-id="6a6af-151">Der Konstruktor sollte jedoch als geschützt markiert werden, sofern die Klasse nicht versiegelt ist. Ist dies der Fall, sollte der Konstruktor als privat markiert werden</span><span class="sxs-lookup"><span data-stu-id="6a6af-151">However, it is a best practice to make the constructor protected unless the class is sealed, in which case the constructor should be marked private.</span></span> <span data-ttu-id="6a6af-152">Der Konstruktor sollte außerdem eine gründliche Validierung der Eingaben durchführen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-152">The constructor should also perform thorough input validation.</span></span> <span data-ttu-id="6a6af-153">Um Missbrauch durch bösartigen Code zu verhindern, muss der Konstruktor dieselben Sicherheitsüberprüfungen und Berechtigungen erzwingen, die zum Abrufen einer Instanz der Klasse durch einen anderen Konstruktor erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6a6af-153">To avoid misuse by malicious code, the constructor should enforce the same security checks and permissions required to obtain an instance of the class using any other constructor.</span></span> <span data-ttu-id="6a6af-154">Wenn Sie diese Empfehlung nicht umsetzen, kann bösartiger Code ein Objekt im Voraus serialisieren. Der Code kann dann mit der Berechtigung [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) unter Angabe des <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter>-Flags die Steuerung übernehmen und das Objekt auf einem Clientcomputer deserialisieren, wobei alle Sicherheitseinstellungen umgangen werden, die bei einer standardmäßigen Instanzerstellung mit einem öffentlichen Konstruktor gelten.</span><span class="sxs-lookup"><span data-stu-id="6a6af-154">If you do not follow this recommendation, malicious code can preserialize an object, obtain control with the [SecurityPermission](xref:System.Security.Permissions.SecurityPermissionAttribute) with the <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter> flag specified and deserialize the object on a client computer bypassing any security that would have been applied during standard instance construction using a public constructor.</span></span>  
  
 <span data-ttu-id="6a6af-155">Um den Zustand des Objekts wiederherzustellen, müssen nur die Werte der Variablen aus <xref:System.Runtime.Serialization.SerializationInfo> mithilfe der bei der Serialisierung verwendeten Namen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6a6af-155">To restore the state of the object, simply retrieve the values of the variables from <xref:System.Runtime.Serialization.SerializationInfo> using the names used during serialization.</span></span> <span data-ttu-id="6a6af-156">Wenn die Basisklasse <xref:System.Runtime.Serialization.ISerializable> implementiert, sollte der Basiskonstruktor aufgerufen werden, damit das Basisobjekt seine Variablen wiederherstellen kann.</span><span class="sxs-lookup"><span data-stu-id="6a6af-156">If the base class implements <xref:System.Runtime.Serialization.ISerializable>, the base constructor should be called to allow the base object to restore its variables.</span></span>  
  
 <span data-ttu-id="6a6af-157">Wenn Sie von einer Klasse, die <xref:System.Runtime.Serialization.ISerializable> implementiert, eine neue Klasse ableiten, muss die abgeleitete Klasse sowohl den Konstruktor als auch die **GetObjectData**-Methode implementieren, wenn sie über zu serialisierende Variablen verfügt.</span><span class="sxs-lookup"><span data-stu-id="6a6af-157">When you derive a new class from one that implements <xref:System.Runtime.Serialization.ISerializable>, the derived class must implement both the constructor as well as the **GetObjectData** method if it has variables that need to be serialized.</span></span> <span data-ttu-id="6a6af-158">Im folgenden Codebeispiel wird dieser Vorgang unter Verwendung der bereits zuvor gezeigten `MyObject`-Klasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6a6af-158">The following code example shows how this is done using the `MyObject` class shown previously.</span></span>  
  
```csharp
[Serializable]
public class ObjectTwo : MyObject
{
    public int num;

    public ObjectTwo()
      : base()
    {
    }

    protected ObjectTwo(SerializationInfo si, StreamingContext context)
      : base(si, context)
    {
        num = si.GetInt32("num");
    }

    [SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter = true)]
    public override void GetObjectData(SerializationInfo si, StreamingContext context)
    {
        base.GetObjectData(si,context);
        si.AddValue("num", num);
    }
}
```

```vb
<Serializable()>  _
Public Class ObjectTwo
    Inherits MyObject
    Public num As Integer

    Public Sub New()

    End Sub

    Protected Sub New(ByVal si As SerializationInfo, _
    ByVal context As StreamingContext)
        MyBase.New(si, context)
        num = si.GetInt32("num")
    End Sub

    <SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)> _
    Public Overrides Sub GetObjectData(ByVal si As SerializationInfo, ByVal context As StreamingContext)
        MyBase.GetObjectData(si, context)
        si.AddValue("num", num)
    End Sub
End Class
```  
  
 <span data-ttu-id="6a6af-159">Vergessen Sie nicht, die Basisklasse im Deserialisierungskonstruktor aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-159">Don't forget to call the base class in the deserialization constructor.</span></span> <span data-ttu-id="6a6af-160">Andernfalls wird der Konstruktor für die Basisklasse nicht aufgerufen, und das Objekt wird nach der Deserialisierung nicht vollständig erstellt.</span><span class="sxs-lookup"><span data-stu-id="6a6af-160">If this isn't done, the constructor on the base class is never called, and the object is not fully constructed after deserialization.</span></span>  
  
 <span data-ttu-id="6a6af-161">Objekte werden von innen nach außen rekonstruiert. Dies bedeutet, dass das Aufrufen von Methoden während der Deserialisierung unerwünschte Nebeneffekte haben kann, wenn sich die aufgerufenen Methoden auf Objektverweise beziehen, die zum Zeitpunkt des Aufrufs noch nicht deserialisiert worden sind.</span><span class="sxs-lookup"><span data-stu-id="6a6af-161">Objects are reconstructed from the inside out; and calling methods during deserialization can have undesirable side effects, because the methods called might refer to object references that have not been deserialized by the time the call is made.</span></span> <span data-ttu-id="6a6af-162">Wenn die deserialisierte Klasse <xref:System.Runtime.Serialization.IDeserializationCallback> implementiert, wird die <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%2A>-Methode automatisch aufgerufen, sobald die gesamte Objektgrafik deserialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6a6af-162">If the class being deserialized implements the <xref:System.Runtime.Serialization.IDeserializationCallback>, the <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%2A> method is automatically called when the entire object graph has been deserialized.</span></span> <span data-ttu-id="6a6af-163">Zu diesem Zeitpunkt sind auch die untergeordneten Objekte, auf die verwiesen wurde, vollständig wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="6a6af-163">At this point, all the child objects referenced have been fully restored.</span></span> <span data-ttu-id="6a6af-164">Eine Hashtabelle ist ein typisches Beispiel für eine Klasse, die ohne Verwendung des Ereignislisteners schwer zu deserialisieren ist.</span><span class="sxs-lookup"><span data-stu-id="6a6af-164">A hash table is a typical example of a class that is difficult to deserialize without using the event listener.</span></span> <span data-ttu-id="6a6af-165">Es ist einfach, die Schlüssel- und Wert-Paare während der Deserialisierung abzurufen. Es kann jedoch problematisch sein, diese Objekte dann wieder der Hashtabelle hinzuzufügen, da nicht gewährleistet ist, dass die von der Hashtabelle abgeleiteten Klassen deserialisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6a6af-165">It is easy to retrieve the key and value pairs during deserialization, but adding these objects back to the hash table can cause problems, because there is no guarantee that classes that derived from the hash table have been deserialized.</span></span> <span data-ttu-id="6a6af-166">Daher wird davon abgeraten, zu diesem Zeitpunkt Methoden für Hashtabellen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6a6af-166">Calling methods on a hash table at this stage is therefore not advisable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a6af-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a6af-167">See also</span></span>

- [<span data-ttu-id="6a6af-168">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="6a6af-168">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="6a6af-169">XML- und SOAP-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="6a6af-169">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="6a6af-170">Sicherheit und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="6a6af-170">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)
