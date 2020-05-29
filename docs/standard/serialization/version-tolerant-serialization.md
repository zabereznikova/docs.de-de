---
title: Versionstolerante Serialisierung
description: In .NET Framework 2.0 wurde Version Tolerant Serialization eingeführt, eine Gruppe von Funktionen, die das Ändern serialisierbarer Typen vereinfachen.
ms.date: 08/08/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- version tolerant serialization
- serialization, custom serialization
- serialization, version tolerant
- serialization, controlling
- versions and serialization
- BinaryFormatter class, samples
- serialization, attributes
ms.assetid: bea0ffe3-2708-4a16-ac7d-e586ed6b8e8d
ms.openlocfilehash: afc822e1f8873bac069f6634fdf1d4665d392e69
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762590"
---
# <a name="version-tolerant-serialization"></a><span data-ttu-id="8e509-103">Versionstolerante Serialisierung</span><span class="sxs-lookup"><span data-stu-id="8e509-103">Version tolerant serialization</span></span>

<span data-ttu-id="8e509-104">In Version&#160;1.0 und Version 1.1 von .NET&#160;Framework war das Erstellen serialisierbarer Typen problematisch, die für mehrere Anwendungsversionen verwendbar waren.</span><span class="sxs-lookup"><span data-stu-id="8e509-104">In version 1.0 and 1.1 of the .NET Framework, creating serializable types that would be reusable from one version of an application to the next was problematic.</span></span> <span data-ttu-id="8e509-105">Wenn ein Typ durch Hinzufügen eines zusätzlicher Felder geändert wurde, traten die folgenden Probleme auf:</span><span class="sxs-lookup"><span data-stu-id="8e509-105">If a type was modified by adding extra fields, the following problems would occur:</span></span>

- <span data-ttu-id="8e509-106">Ältere Versionen einer Anwendung lösten bei dem Versuch, neue Versionen des alten Typs zu deserialisieren, Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="8e509-106">Older versions of an application would throw exceptions when asked to deserialize new versions of the old type.</span></span>
- <span data-ttu-id="8e509-107">Neuere Versionen einer Anwendung lösten bei dem Versuch, ältere Versionen eines Typs mit fehlenden Daten zu deserialisieren, Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="8e509-107">Newer versions of an application would throw exceptions when deserializing older versions of a type with missing data.</span></span>

<span data-ttu-id="8e509-108">Bei VTS (Version Tolerant Serialization) handelt es sich um eine Gruppe von Funktionen, die in .NET&#160;Framework&#160;2.0 eingeführt wurde, um das möglicherweise im Laufe der Zeit erforderliche Ändern serialisierbarer Typen zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="8e509-108">Version Tolerant Serialization (VTS) is a set of features introduced in .NET Framework 2.0 that makes it easier, over time, to modify serializable types.</span></span> <span data-ttu-id="8e509-109">Die VTS-Funktionen sind insbesondere für Klassen aktiviert, auf die das <xref:System.SerializableAttribute>-Attribut angewendet wurde, einschließlich generischer Typen.</span><span class="sxs-lookup"><span data-stu-id="8e509-109">Specifically, the VTS features are enabled for classes to which the <xref:System.SerializableAttribute> attribute has been applied, including generic types.</span></span> <span data-ttu-id="8e509-110">VTS ermöglicht das Hinzufügen neuer Felder zu diesen Klassen, ohne die Kompatibilität mit anderen Versionen des Typs zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="8e509-110">VTS makes it possible to add new fields to those classes without breaking compatibility with other versions of the type.</span></span> <span data-ttu-id="8e509-111">Informationen zu einer funktionierenden Beispielanwendung finden Sie unter [Technologiebeispiel für versionstolerante Serialisierung](basic-serialization-technology-sample.md).</span><span class="sxs-lookup"><span data-stu-id="8e509-111">For a working sample application, see [Version Tolerant Serialization Technology Sample](basic-serialization-technology-sample.md).</span></span>

<span data-ttu-id="8e509-112">Die VTS-Funktionen werden bei der Verwendung von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8e509-112">The VTS features are enabled when using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span> <span data-ttu-id="8e509-113">Zudem sind alle Funktionen mit Ausnahme der Toleranz für externe Daten auch bei der Verwendung von <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8e509-113">Additionally, all features except extraneous data tolerance are also enabled when using the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span></span> <span data-ttu-id="8e509-114">Weitere Informationen zur Verwendung dieser Klassen für die Serialisierung finden Sie unter [Binäre Serialisierung](binary-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="8e509-114">For more information about using these classes for serialization, see [Binary Serialization](binary-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

## <a name="feature-list"></a><span data-ttu-id="8e509-115">Funktionsliste</span><span class="sxs-lookup"><span data-stu-id="8e509-115">Feature list</span></span>

<span data-ttu-id="8e509-116">VTS umfasst die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="8e509-116">The set of features includes the following:</span></span>

- <span data-ttu-id="8e509-117">Toleranz für externe oder unerwartete Daten.</span><span class="sxs-lookup"><span data-stu-id="8e509-117">Tolerance of extraneous or unexpected data.</span></span> <span data-ttu-id="8e509-118">Dies ermöglicht es neueren Versionen des Typs, Daten an frühere Versionen zu senden.</span><span class="sxs-lookup"><span data-stu-id="8e509-118">This enables newer versions of the type to send data to older versions.</span></span>
- <span data-ttu-id="8e509-119">Toleranz für fehlende optionale Daten.</span><span class="sxs-lookup"><span data-stu-id="8e509-119">Tolerance of missing optional data.</span></span> <span data-ttu-id="8e509-120">Dies ermöglicht es älteren Versionen, Daten an neuere Versionen zu senden.</span><span class="sxs-lookup"><span data-stu-id="8e509-120">This enables older versions to send data to newer versions.</span></span>
- <span data-ttu-id="8e509-121">Serialisierungsrückrufe.</span><span class="sxs-lookup"><span data-stu-id="8e509-121">Serialization callbacks.</span></span> <span data-ttu-id="8e509-122">Dies ermöglicht ein intelligentes Festlegen von Standardwerten im Fall fehlender Daten.</span><span class="sxs-lookup"><span data-stu-id="8e509-122">This enables intelligent default value setting in cases where data is missing.</span></span>

<span data-ttu-id="8e509-123">Zudem ist eine Funktion zum Deklarieren verfügbar, wenn ein neues optionales Feld hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="8e509-123">In addition, there is a feature for declaring when a new optional field has been added.</span></span> <span data-ttu-id="8e509-124">Es handelt sich hierbei um die <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A>-Eigenschaft des <xref:System.Runtime.Serialization.OptionalFieldAttribute>-Attributs.</span><span class="sxs-lookup"><span data-stu-id="8e509-124">This is the <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A> property of the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute.</span></span>

<span data-ttu-id="8e509-125">Diese Funktionen werden in den folgenden Abschnitten ausführlicher erläutert.</span><span class="sxs-lookup"><span data-stu-id="8e509-125">These features are discussed in greater detail in the following sections.</span></span>

### <a name="tolerance-of-extraneous-or-unexpected-data"></a><span data-ttu-id="8e509-126">Toleranz für externe oder unerwartete Daten</span><span class="sxs-lookup"><span data-stu-id="8e509-126">Tolerance of extraneous or unexpected data</span></span>

<span data-ttu-id="8e509-127">In früheren Versionen wurden während der Deserialisierung bei auftretenden externen oder unerwarteten Daten Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="8e509-127">In the past, during deserialization, any extraneous or unexpected data caused exceptions to be thrown.</span></span> <span data-ttu-id="8e509-128">Mit VTS werden in derselben Situation keine Ausnahmen mehr ausgelöst, sondern alle externen oder unerwarteten Daten werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8e509-128">With VTS, in the same situation, any extraneous or unexpected data is ignored instead of causing exceptions to be thrown.</span></span> <span data-ttu-id="8e509-129">Dies ermöglicht es, Anwendungen mit neueren Versionen eines Typs (d.&#160;h. eine Version mit mehr Feldern), Informationen an Anwendungen zu senden, die ältere Versionen desselben Typs erwarten.</span><span class="sxs-lookup"><span data-stu-id="8e509-129">This enables applications that use newer versions of a type (that is, a version that includes more fields) to send information to applications that expect older versions of the same type.</span></span>

<span data-ttu-id="8e509-130">Im folgenden Beispiel werden die zusätzlichen Daten im `CountryField`-Feld von Version&#160;2.0 der `Address`-Klasse ignoriert, wenn eine ältere Anwendung die neuere Version deserialisiert.</span><span class="sxs-lookup"><span data-stu-id="8e509-130">In the following example, the extra data contained in the `CountryField` of version 2.0 of the `Address` class is ignored when an older application deserializes the newer version.</span></span>

```csharp  
// Version 1 of the Address class.  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
}  
// Version 2.0 of the Address class.  
[Serializable]  
public class Address  
{  
    public string Street;  
    public string City;  
    // The older application ignores this data.  
    public string CountryField;  
}  
```  
  
```vb  
' Version 1 of the Address class.  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
End Class  
  
' Version 2.0 of the Address class.  
<Serializable> _  
Public Class Address  
    Public Street As String  
    Public City As String  
    ' The older application ignores this data.  
    Public CountryField As String  
End Class  
```  

### <a name="tolerance-of-missing-data"></a><span data-ttu-id="8e509-131">Toleranz für fehlende Daten</span><span class="sxs-lookup"><span data-stu-id="8e509-131">Tolerance of missing data</span></span>

<span data-ttu-id="8e509-132">Felder können mithilfe des <xref:System.Runtime.Serialization.OptionalFieldAttribute>-Attributs als optional markiert werden.</span><span class="sxs-lookup"><span data-stu-id="8e509-132">Fields can be marked as optional by applying the <xref:System.Runtime.Serialization.OptionalFieldAttribute> attribute to them.</span></span> <span data-ttu-id="8e509-133">Wenn während der Deserialisierung optionale Daten fehlen, ignoriert die Serialisierungs-Engine das Fehlen dieser Daten und löst keine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="8e509-133">During deserialization, if the optional data is missing, the serialization engine ignores the absence and does not throw an exception.</span></span> <span data-ttu-id="8e509-134">Anwendungen, die ältere Versionen eines Typs erwarten, können daher Daten an Anwendungen senden, die neuere Versionen desselben Typs erwarten.</span><span class="sxs-lookup"><span data-stu-id="8e509-134">Thus, applications that expect older versions of a type can send data to applications that expect newer versions of the same type.</span></span>

<span data-ttu-id="8e509-135">Im folgenden Beispiel wird Version&#160;2.0 der `Address`-Klasse mit dem als optional markierten `CountryField`-Feld veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8e509-135">The following example shows version 2.0 of the `Address` class with the `CountryField` field marked as optional.</span></span> <span data-ttu-id="8e509-136">Wenn eine ältere Anwendung Version&#160;1 an eine neuere Anwendung sendet, die Version&#160;2.0 erwartet, wird das Fehlen der Daten ignoriert.</span><span class="sxs-lookup"><span data-stu-id="8e509-136">If an older application sends version 1 to a newer application that expects version 2.0, the absence of the data is ignored.</span></span>

```csharp
[Serializable]
public class Address
{
    public string Street;
    public string City;

    [OptionalField]
    public string CountryField;
}
```

```vb
<Serializable> _
Public Class Address
    Public Street As String
    Public City As String

    <OptionalField> _
    Public CountryField As String
End Class
```
  
### <a name="serialization-callbacks"></a><span data-ttu-id="8e509-137">Serialisierungsrückrufe</span><span class="sxs-lookup"><span data-stu-id="8e509-137">Serialization callbacks</span></span>

<span data-ttu-id="8e509-138">Serialisierungsrückrufe stellen einen Mechanismus dar, der an vier Punkten im Serialisierungs-/Deserialisierungsprozess Hooks bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="8e509-138">Serialization callbacks are a mechanism that provides hooks into the serialization/deserialization process at four points.</span></span>

|<span data-ttu-id="8e509-139">Attribut</span><span class="sxs-lookup"><span data-stu-id="8e509-139">Attribute</span></span>|<span data-ttu-id="8e509-140">Beim Aufruf der verknüpften Methode</span><span class="sxs-lookup"><span data-stu-id="8e509-140">When the Associated Method is Called</span></span>|<span data-ttu-id="8e509-141">Typische Verwendung</span><span class="sxs-lookup"><span data-stu-id="8e509-141">Typical Use</span></span>|
|---------------|------------------------------------------|-----------------|
|<xref:System.Runtime.Serialization.OnDeserializingAttribute>|<span data-ttu-id="8e509-142">Vor der Deserialisierung.\*</span><span class="sxs-lookup"><span data-stu-id="8e509-142">Before deserialization.\*</span></span>|<span data-ttu-id="8e509-143">Initialisieren von Standardwerten für optionale Felder.</span><span class="sxs-lookup"><span data-stu-id="8e509-143">Initialize default values for optional fields.</span></span>|
|<xref:System.Runtime.Serialization.OnDeserializedAttribute>|<span data-ttu-id="8e509-144">Nach der Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="8e509-144">After deserialization.</span></span>|<span data-ttu-id="8e509-145">Korrigieren Sie optionale Feldwerte auf der Grundlage des Inhalts anderer Felder.</span><span class="sxs-lookup"><span data-stu-id="8e509-145">Fix optional field values based on contents of other fields.</span></span>|
|<xref:System.Runtime.Serialization.OnSerializingAttribute>|<span data-ttu-id="8e509-146">Vor der Deserialisierung.</span><span class="sxs-lookup"><span data-stu-id="8e509-146">Before serialization.</span></span>|<span data-ttu-id="8e509-147">Vorbereiten der Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="8e509-147">Prepare for serialization.</span></span> <span data-ttu-id="8e509-148">Erstellen Sie z.&#160;B. optionale Datenstrukturen.</span><span class="sxs-lookup"><span data-stu-id="8e509-148">For example, create optional data structures.</span></span>|
|<xref:System.Runtime.Serialization.OnSerializedAttribute>|<span data-ttu-id="8e509-149">Nach der Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="8e509-149">After serialization.</span></span>|<span data-ttu-id="8e509-150">Protokollieren der Serialisierungsereignisse.</span><span class="sxs-lookup"><span data-stu-id="8e509-150">Log serialization events.</span></span>|

 <span data-ttu-id="8e509-151">\* Dieser Rückruf wird vor dem Deserialisierungskonstruktor aufgerufen, sofern ein solcher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8e509-151">\* This callback is invoked before the deserialization constructor, if one is present.</span></span>

#### <a name="using-callbacks"></a><span data-ttu-id="8e509-152">Verwenden von Rückrufen</span><span class="sxs-lookup"><span data-stu-id="8e509-152">Using callbacks</span></span>

<span data-ttu-id="8e509-153">Zur Verwendung von Rückrufen wenden Sie die entsprechenden Attribute auf eine Methode an, die einen <xref:System.Runtime.Serialization.StreamingContext>-Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="8e509-153">To use callbacks, apply the appropriate attribute to a method that accepts a <xref:System.Runtime.Serialization.StreamingContext> parameter.</span></span> <span data-ttu-id="8e509-154">Mit jedem dieser Attribute kann nur eine Methode pro Klasse markiert werden.</span><span class="sxs-lookup"><span data-stu-id="8e509-154">Only one method per class can be marked with each of these attributes.</span></span> <span data-ttu-id="8e509-155">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e509-155">For example:</span></span>

```csharp
[OnDeserializing]
private void SetCountryRegionDefault(StreamingContext sc)
{
    CountryField = "Japan";
}
```

```vb
<OnDeserializing>
Private Sub SetCountryRegionDefault(sc As StreamingContext)
    CountryField = "Japan"
End Sub
```

<span data-ttu-id="8e509-156">Diese Methoden sind für die Versionsverwaltung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8e509-156">The intended use of these methods is for versioning.</span></span> <span data-ttu-id="8e509-157">Während der Deserialisierung wird ein optionales Feld möglicherweise nicht korrekt initialisiert, wenn die Daten für das Feld fehlen.</span><span class="sxs-lookup"><span data-stu-id="8e509-157">During deserialization, an optional field may not be correctly initialized if the data for the field is missing.</span></span> <span data-ttu-id="8e509-158">Dies kann korrigiert werden, indem zunächst die Methode erstellt wird, die den richtigen Wert zuordnet, und dann entweder das **OnDeserializingAttribute**- oder **OnDeserializedAttribute**-Attribut auf die Methode angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="8e509-158">This can be corrected by creating the method that assigns the correct value, then applying either the **OnDeserializingAttribute** or **OnDeserializedAttribute** attribute to the method.</span></span>

<span data-ttu-id="8e509-159">Im folgenden Beispiel wird die Methode im Kontext eines Typs veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8e509-159">The following example shows the method in the context of a type.</span></span> <span data-ttu-id="8e509-160">Wenn eine frühere Version einer Anwendung eine Instanz der`Address`-Klasse an eine höhere Version der Anwendung sendet, fehlen Daten im `CountryField`-Feld.</span><span class="sxs-lookup"><span data-stu-id="8e509-160">If an earlier version of an application sends an instance of the `Address` class to a later version of the application, the `CountryField` field data will be missing.</span></span> <span data-ttu-id="8e509-161">Nach der Deserialisierung wird das Feld jedoch auf den Standardwert „Japan“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8e509-161">But after deserialization, the field will be set to a default value "Japan".</span></span>

```csharp
[Serializable]
public class Address
{
    public string Street;
    public string City;
    [OptionalField]
    public string CountryField;

    [OnDeserializing]
    private void SetCountryRegionDefault(StreamingContext sc)
    {
        CountryField = "Japan";
    }
}
```

```vb
<Serializable> _
Public Class Address
    Public Street As String
    Public City As String
    <OptionalField> _
    Public CountryField As String

    <OnDeserializing> _
    Private Sub SetCountryRegionDefault(sc As StreamingContext)
        CountryField = "Japan"
    End Sub
End Class
```

## <a name="the-versionadded-property"></a><span data-ttu-id="8e509-162">Die VersionAdded-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8e509-162">The VersionAdded property</span></span>

<span data-ttu-id="8e509-163">Das **OptionalFieldAttribute** verfügt über die **VersionAdded**-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8e509-163">The **OptionalFieldAttribute** has the **VersionAdded** property.</span></span> <span data-ttu-id="8e509-164">In Version 2.0 von .NET Framework wird diese nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e509-164">In version 2.0 of the .NET Framework, this isn't used.</span></span> <span data-ttu-id="8e509-165">Es ist jedoch wichtig, dass diese Eigenschaft richtig festgelegt wird, um sicherzustellen, dass der Typ mit zukünftigen Serialisierungs-Engines kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="8e509-165">However, it's important to set this property correctly to ensure that the type will be compatible with future serialization engines.</span></span>

<span data-ttu-id="8e509-166">Die Eigenschaft gibt an, welche Version eines Typs einem bestimmten Feld hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="8e509-166">The property indicates which version of a type a given field has been added.</span></span> <span data-ttu-id="8e509-167">Sie sollte bei jeder Änderung des Typs um genau 1 erhöht werden (ausgehend von 2). Dies veranschaulicht das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e509-167">It should be incremented by exactly one (starting at 2) every time the type is modified, as shown in the following example:</span></span>

```csharp
// Version 1.0
[Serializable]
public class Person
{
    public string FullName;
}

// Version 2.0
[Serializable]
public class Person
{
    public string FullName;

    [OptionalField(VersionAdded = 2)]
    public string NickName;
    [OptionalField(VersionAdded = 2)]
    public DateTime BirthDate;
}

// Version 3.0
[Serializable]
public class Person
{
    public string FullName;

    [OptionalField(VersionAdded=2)]
    public string NickName;
    [OptionalField(VersionAdded=2)]
    public DateTime BirthDate;

    [OptionalField(VersionAdded=3)]
    public int Weight;
}
```

```vb
' Version 1.0
<Serializable> _
Public Class Person
    Public FullName
End Class

' Version 2.0
<Serializable> _
Public Class Person
    Public FullName As String

    <OptionalField(VersionAdded := 2)> _
    Public NickName As String
    <OptionalField(VersionAdded := 2)> _
    Public BirthDate As DateTime
End Class

' Version 3.0
<Serializable> _
Public Class Person
    Public FullName As String

    <OptionalField(VersionAdded := 2)> _
    Public NickName As String
    <OptionalField(VersionAdded := 2)> _
    Public BirthDate As DateTime

    <OptionalField(VersionAdded := 3)> _
    Public Weight As Integer
End Class
```

## <a name="serializationbinder"></a><span data-ttu-id="8e509-168">SerializationBinder</span><span class="sxs-lookup"><span data-stu-id="8e509-168">SerializationBinder</span></span>

<span data-ttu-id="8e509-169">Einige Benutzer müssen möglicherweise steuern, welche Klasse serialisiert und deserialisiert werden soll, da unterschiedliche Versionen der Klasse auf dem Server und Client erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8e509-169">Some users may need to control which class to serialize and deserialize because a different version of the class is required on the server and client.</span></span> <span data-ttu-id="8e509-170"><xref:System.Runtime.Serialization.SerializationBinder> ist eine abstrakte Klasse, mit der die tatsächlichen Typen gesteuert werden, die während der Serialisierung und Deserialisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e509-170"><xref:System.Runtime.Serialization.SerializationBinder> is an abstract class used to control the actual types used during serialization and deserialization.</span></span> <span data-ttu-id="8e509-171">Wenn Sie diese Klasse verwenden möchten, müssen Sie eine Klasse von <xref:System.Runtime.Serialization.SerializationBinder> ableiten und die <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A>-Methode und die <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>-Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="8e509-171">To use this class, derive a class from <xref:System.Runtime.Serialization.SerializationBinder> and override the <xref:System.Runtime.Serialization.SerializationBinder.BindToName%2A> and <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> methods.</span></span> <span data-ttu-id="8e509-172">Weitere Informationen finden Sie unter [Steuern der Serialisierung und Deserialisierung mit SerializationBinder](../../framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md).</span><span class="sxs-lookup"><span data-stu-id="8e509-172">For more information, see [Controlling Serialization and Deserialization with SerializationBinder](../../framework/wcf/feature-details/controlling-serialization-and-deserialization-with-serializationbinder.md).</span></span>

## <a name="best-practices"></a><span data-ttu-id="8e509-173">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="8e509-173">Best practices</span></span>

<span data-ttu-id="8e509-174">Um das richtige Versionsverhalten sicherzustellen, beachten Sie beim Ändern eines Typs von Version zu Version die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="8e509-174">To ensure proper versioning behavior, follow these rules when modifying a type from version to version:</span></span>

- <span data-ttu-id="8e509-175">Entfernen Sie nie ein serialisiertes Feld.</span><span class="sxs-lookup"><span data-stu-id="8e509-175">Never remove a serialized field.</span></span>
- <span data-ttu-id="8e509-176">Wenden Sie das <xref:System.NonSerializedAttribute>-Attribut nie auf ein Feld an, wenn das Attribut in der vorherigen Version nicht auf das Feld angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8e509-176">Never apply the <xref:System.NonSerializedAttribute> attribute to a field if the attribute was not applied to the field in the previous version.</span></span>
- <span data-ttu-id="8e509-177">Ändern Sie nie den Namen oder den Typ eines serialisierten Felds.</span><span class="sxs-lookup"><span data-stu-id="8e509-177">Never change the name or the type of a serialized field.</span></span>
- <span data-ttu-id="8e509-178">Wenden Sie beim Hinzufügen eines neuen serialisierten Felds das **OptionalFieldAttribute**-Attribut an.</span><span class="sxs-lookup"><span data-stu-id="8e509-178">When adding a new serialized field, apply the **OptionalFieldAttribute** attribute.</span></span>
- <span data-ttu-id="8e509-179">Wenden Sie beim Entfernen eines **NonSerializedAttribute**-Attributs von einem Feld, das in einer vorherigen Version nicht serialisierbar war, das **OptionalFieldAttribute**-Attribut an.</span><span class="sxs-lookup"><span data-stu-id="8e509-179">When removing a **NonSerializedAttribute** attribute from a field (that was not serializable in a previous version), apply the **OptionalFieldAttribute** attribute.</span></span>
- <span data-ttu-id="8e509-180">Legen Sie für alle optionalen Felder sinnvolle Standardwerte fest, indem Sie die Serialisierungsrückrufe verwenden, sofern 0 oder **NULL** nicht als Standardwerte zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="8e509-180">For all optional fields, set meaningful defaults using the serialization callbacks unless 0 or **null** as defaults are acceptable.</span></span>

<span data-ttu-id="8e509-181">Um sicherzustellen, dass ein Typ mit zukünftigen Serialisierungs-Engines kompatibel ist, beachten Sie die folgenden Richtlinien:</span><span class="sxs-lookup"><span data-stu-id="8e509-181">To ensure that a type will be compatible with future serialization engines, follow these guidelines:</span></span>

- <span data-ttu-id="8e509-182">Legen Sie die **VersionAdded**-Eigenschaft im **OptionalFieldAttribute**-Attribut ordnungsgemäß fest.</span><span class="sxs-lookup"><span data-stu-id="8e509-182">Always set the **VersionAdded** property on the **OptionalFieldAttribute** attribute correctly.</span></span>
- <span data-ttu-id="8e509-183">Vermeiden Sie verzweigte Versionen.</span><span class="sxs-lookup"><span data-stu-id="8e509-183">Avoid branched versioning.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e509-184">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e509-184">See also</span></span>

- <xref:System.SerializableAttribute>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>
- <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>
- <xref:System.Runtime.Serialization.OptionalFieldAttribute.VersionAdded%2A>
- <xref:System.Runtime.Serialization.OptionalFieldAttribute>
- <xref:System.Runtime.Serialization.OnDeserializingAttribute>
- <xref:System.Runtime.Serialization.OnDeserializedAttribute>
- <xref:System.Runtime.Serialization.OnSerializingAttribute>
- <xref:System.Runtime.Serialization.OnSerializedAttribute>
- <xref:System.Runtime.Serialization.StreamingContext>
- <xref:System.NonSerializedAttribute>
- [<span data-ttu-id="8e509-185">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="8e509-185">Binary Serialization</span></span>](binary-serialization.md)
