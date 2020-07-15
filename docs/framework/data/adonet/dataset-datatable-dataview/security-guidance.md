---
title: Leitfaden für DataSet und Datentabelle
ms.date: 07/14/2020
dev_langs:
- csharp
ms.openlocfilehash: c6b32afeadccc3fd22d6611d282840233280440f
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86382467"
---
# <a name="dataset-and-datatable-security-guidance"></a><span data-ttu-id="e87c7-102">Leitfaden für DataSet und Datentabelle</span><span class="sxs-lookup"><span data-stu-id="e87c7-102">DataSet and DataTable security guidance</span></span>

<span data-ttu-id="e87c7-103">Dieser Artikel bezieht sich auf:</span><span class="sxs-lookup"><span data-stu-id="e87c7-103">This article applies to:</span></span>

* <span data-ttu-id="e87c7-104">.NET Framework (alle Versionen)</span><span class="sxs-lookup"><span data-stu-id="e87c7-104">.NET Framework (all versions)</span></span>
* <span data-ttu-id="e87c7-105">.Net Core und höher</span><span class="sxs-lookup"><span data-stu-id="e87c7-105">.NET Core and later</span></span>
* <span data-ttu-id="e87c7-106">.Net 5,0 und höher</span><span class="sxs-lookup"><span data-stu-id="e87c7-106">.NET 5.0 and later</span></span>

<span data-ttu-id="e87c7-107">Bei [DataSets](/dotnet/api/system.data.dataset) und [Datentypen handelt](/dotnet/api/system.data.datatable) es sich um Legacy-.NET-Komponenten, die das darstellen von Datasets als verwaltete Objekte ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-107">The [DataSet](/dotnet/api/system.data.dataset) and [DataTable](/dotnet/api/system.data.datatable) types are legacy .NET components that allow representing data sets as managed objects.</span></span> <span data-ttu-id="e87c7-108">Diese Komponenten wurden in .NET 1,0 als Teil der ursprünglichen ADO.net- [Infrastruktur](/dotnet/framework/data/adonet/dataset-datatable-dataview/)eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-108">These components were introduced in .NET 1.0 as part of the original [ADO.NET infrastructure](/dotnet/framework/data/adonet/dataset-datatable-dataview/).</span></span> <span data-ttu-id="e87c7-109">Ihr Ziel bestand darin, eine verwaltete Sicht über ein relationales Dataset bereitzustellen und dabei zu abstrahieren, ob die zugrunde liegende Quelle der Daten XML, SQL oder eine andere Technologie war.</span><span class="sxs-lookup"><span data-stu-id="e87c7-109">Their goal was to provide a managed view over a relational data set, abstracting away whether the underlying source of the data was XML, SQL, or another technology.</span></span>

<span data-ttu-id="e87c7-110">Weitere Informationen zu ADO.net, einschließlich modernerer Daten Ansichts Paradigmen, finden Sie in [der ADO.NET-Dokumentation](/dotnet/framework/data/adonet/).</span><span class="sxs-lookup"><span data-stu-id="e87c7-110">For more information on ADO.NET, including more modern data view paradigms, see [the ADO.NET documentation](/dotnet/framework/data/adonet/).</span></span>

## <a name="default-restrictions-when-deserializing-a-dataset-or-datatable-from-xml"></a><span data-ttu-id="e87c7-111">Standard Einschränkungen beim Deserialisieren eines Datasets oder einer Datentabelle aus XML</span><span class="sxs-lookup"><span data-stu-id="e87c7-111">Default restrictions when deserializing a DataSet or DataTable from XML</span></span>

<span data-ttu-id="e87c7-112">Unter allen unterstützten Versionen von .NET Framework, .net Core und .net, `DataSet` und `DataTable` legen Sie die folgenden Einschränkungen für die Typen von Objekten in den deserialisierten Daten ab.</span><span class="sxs-lookup"><span data-stu-id="e87c7-112">On all supported versions of .NET Framework, .NET Core, and .NET, `DataSet` and `DataTable` place the following restrictions on what types of objects may be present in the deserialized data.</span></span> <span data-ttu-id="e87c7-113">Standardmäßig ist diese Liste auf Folgendes beschränkt:</span><span class="sxs-lookup"><span data-stu-id="e87c7-113">By default, this list is restricted to:</span></span>

* <span data-ttu-id="e87c7-114">Primitive und primitive Entsprechungen: `bool` , `char` , `sbyte` , `byte` , `short` , `ushort` , `int` , `uint` , `long` , `ulong` , `float` , `double` , `decimal` , `DateTime` , `DateTimeOffset` , `TimeSpan` , `string` , `Guid` , `SqlBinary` , `SqlBoolean` , `SqlByte` , `SqlBytes` , `SqlChars` , `SqlDateTime` , `SqlDecimal` , `SqlDouble` , `SqlGuid` , `SqlInt16` , `SqlInt32` ,,, `SqlInt64` `SqlMoney` `SqlSingle` und `SqlString` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-114">Primitives and primitive equivalents: `bool`, `char`, `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `decimal`, `DateTime`, `DateTimeOffset`, `TimeSpan`, `string`, `Guid`, `SqlBinary`, `SqlBoolean`, `SqlByte`, `SqlBytes`, `SqlChars`, `SqlDateTime`, `SqlDecimal`, `SqlDouble`, `SqlGuid`, `SqlInt16`, `SqlInt32`, `SqlInt64`, `SqlMoney`, `SqlSingle`, and `SqlString`.</span></span>
* <span data-ttu-id="e87c7-115">Häufig verwendete nicht primitive: `Type` , `Uri` und `BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-115">Commonly used non-primitives: `Type`, `Uri`, and `BigInteger`.</span></span>
* <span data-ttu-id="e87c7-116">Häufig verwendete _System. Drawing_ -Typen: `Color` , `Point` , `PointF` , `Rectangle` , `RectangleF` , `Size` und `SizeF` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-116">Commonly used _System.Drawing_ types: `Color`, `Point`, `PointF`, `Rectangle`, `RectangleF`, `Size`, and `SizeF`.</span></span>
* <span data-ttu-id="e87c7-117">`Enum`solche.</span><span class="sxs-lookup"><span data-stu-id="e87c7-117">`Enum` types.</span></span>
* <span data-ttu-id="e87c7-118">Arrays und Listen der oben genannten Typen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-118">Arrays and lists of the above types.</span></span>

<span data-ttu-id="e87c7-119">Wenn die eingehenden XML-Daten ein Objekt enthalten, dessen Typ nicht in dieser Liste enthalten ist:</span><span class="sxs-lookup"><span data-stu-id="e87c7-119">If the incoming XML data contains an object whose type is not in this list:</span></span>

* <span data-ttu-id="e87c7-120">Es wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e87c7-120">An exception is thrown.</span></span>
* <span data-ttu-id="e87c7-121">Der Deserialisierungsvorgang schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="e87c7-121">The deserialization operation fails.</span></span>

<span data-ttu-id="e87c7-122">Beim Laden von XML in eine vorhandene- `DataSet` Instanz oder- `DataTable` Instanz werden die vorhandenen Spaltendefinitionen ebenfalls berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-122">When loading XML into an existing `DataSet` or `DataTable` instance, the existing column definitions are also taken into account.</span></span> <span data-ttu-id="e87c7-123">Wenn die Tabelle bereits eine Spaltendefinition eines benutzerdefinierten Typs enthält, wird dieser Typ für die Dauer des XML-Deserialisierungsvorgangs vorübergehend zur Zulassungsliste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-123">If the table already contains a column definition of a custom type, that type is temporarily added to the allow list for the duration of the XML deserialization operation.</span></span>

```cs
XmlReader xmlReader = GetXmlReader();

// Assume the XML blob contains data for type MyCustomClass.
// The following call to ReadXml fails because MyCustomClass isn't in the allowed types list.

DataTable table = new DataTable("MyDataTable");
table.ReadXml(xmlReader);

// However, the following call to ReadXml succeeds, since the DataTable instance
// already defines a column of type MyCustomClass.

DataTable table = new DataTable("MyDataTable");
table.Columns.Add("MyColumn", typeof(MyCustomClass));
table.ReadXml(xmlReader); // this call will succeed
```

<span data-ttu-id="e87c7-124">Die Objekttyp Einschränkungen gelten auch, wenn verwendet wird `XmlSerializer` , um eine Instanz von oder zu deserialisieren `DataSet` `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-124">The object type restrictions also apply when using `XmlSerializer` to deserialize an instance of `DataSet` or `DataTable`.</span></span> <span data-ttu-id="e87c7-125">Sie sind jedoch möglicherweise nicht anwendbar, wenn Sie verwenden `BinaryFormatter` , um eine Instanz von oder zu deserialisieren `DataSet` `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-125">However, they may not apply when using `BinaryFormatter` to deserialize an instance of `DataSet` or `DataTable`.</span></span>

<span data-ttu-id="e87c7-126">Die Objekttyp Einschränkungen gelten nicht bei der Verwendung `DataAdapter.Fill` von, z. b. Wenn eine- `DataTable` Instanz ohne Verwendung der XML-deserialisierungsapis direkt aus einer Datenbank aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="e87c7-126">The object type restrictions don't apply when using `DataAdapter.Fill`, such as when a `DataTable` instance is populated directly from a database without using the XML deserialization APIs.</span></span>

### <a name="extend-the-list-of-allowed-types"></a><span data-ttu-id="e87c7-127">Erweitern der Liste der zulässigen Typen</span><span class="sxs-lookup"><span data-stu-id="e87c7-127">Extend the list of allowed types</span></span>

<span data-ttu-id="e87c7-128">Eine APP kann die Liste der zulässigen Typen erweitern und zusätzlich zu den oben aufgeführten integrierten Typen auch benutzerdefinierte Typen einschließen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-128">An app can extend the allowed types list to include custom types in addition to the built-in types listed above.</span></span> <span data-ttu-id="e87c7-129">Wenn Sie die Liste der zulässigen Typen erweitern, wirkt sich die Änderung auf _alle_ `DataSet` -und- `DataTable` Instanzen innerhalb der APP aus.</span><span class="sxs-lookup"><span data-stu-id="e87c7-129">If extending the allowed types list, the change affects _all_ `DataSet` and `DataTable` instances within the app.</span></span> <span data-ttu-id="e87c7-130">Typen können nicht aus der Liste der integrierten Typen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="e87c7-130">Types cannot be removed from the built-in allowed types list.</span></span>

#### <a name="extend-through-configuration-net-framework-40---48"></a><span data-ttu-id="e87c7-131">Erweiterung durch Konfiguration (.NET Framework 4,0-4,8)</span><span class="sxs-lookup"><span data-stu-id="e87c7-131">Extend through configuration (.NET Framework 4.0 - 4.8)</span></span>

<span data-ttu-id="e87c7-132">_App.config_ kann verwendet werden, um die Liste der zulässigen Typen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e87c7-132">_App.config_ can be used to extend the allowed types list.</span></span> <span data-ttu-id="e87c7-133">So erweitern Sie die Liste der zulässigen Typen:</span><span class="sxs-lookup"><span data-stu-id="e87c7-133">To extend the allowed types list:</span></span>

* <span data-ttu-id="e87c7-134">Verwenden Sie das- `<configSections>` Element, um einen Verweis auf den _System. Data_ -Konfigurations Abschnitt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-134">Use the `<configSections>` element to add a reference to the _System.Data_ configuration section.</span></span>
* <span data-ttu-id="e87c7-135">Verwenden `<system.data.dataset.serialization>` / `<allowedTypes>` Sie, um zusätzliche Typen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e87c7-135">Use `<system.data.dataset.serialization>`/`<allowedTypes>` to specify additional types.</span></span>

<span data-ttu-id="e87c7-136">Jedes `<add>` Element muss mithilfe seines qualifizierten Assemblynamens nur einen Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="e87c7-136">Each `<add>` element must specify only one type by using its assembly qualified type name.</span></span> <span data-ttu-id="e87c7-137">Verwenden Sie mehrere-Elemente, um der Liste der zulässigen Typen weitere Typen hinzuzufügen `<add>` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-137">To add additional types to the allowed types list, use multiple `<add>` elements.</span></span>

<span data-ttu-id="e87c7-138">Im folgenden Beispiel wird gezeigt, wie die Liste der zulässigen Typen durch Hinzufügen des benutzerdefinierten Typs erweitert wird `Fabrikam.CustomType` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-138">The following sample shows extending the allowed types list by adding the custom type `Fabrikam.CustomType`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add type="assembly qualified type name" /> -->
      <add type="Fabrikam.CustomType, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
      <!-- additional <add /> elements as needed -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

<span data-ttu-id="e87c7-139">Verwenden Sie zum Abrufen des qualifizierten [Assemblynamens eines Typs die Type. AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) -Eigenschaft, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-139">To retrieve the assembly qualified name of a type, use the [Type.AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) property, as demonstrated in the following code.</span></span>

```cs
string assemblyQualifiedName = typeof(Fabrikam.CustomType).AssemblyQualifiedName;
```

<a name="etc"></a>

#### <a name="extend-through-configuration-net-framework-20---35"></a><span data-ttu-id="e87c7-140">Erweiterung durch Konfiguration (.NET Framework 2,0-3,5)</span><span class="sxs-lookup"><span data-stu-id="e87c7-140">Extend through configuration (.NET Framework 2.0 - 3.5)</span></span>

<span data-ttu-id="e87c7-141">Wenn Ihre APP auf .NET Framework 2,0 oder 3,5 ausgerichtet ist, können Sie weiterhin den oben genannten _App.config_ Mechanismus verwenden, um die Liste der zulässigen Typen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="e87c7-141">If your app targets .NET Framework 2.0 or 3.5, you can still use the above _App.config_ mechanism to extend the allowed types list.</span></span> <span data-ttu-id="e87c7-142">`<configSections>`Das-Element sieht jedoch etwas anders aus, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e87c7-142">However, your `<configSections>` element will look slightly different, as shown in the following code:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- The below <sectionGroup> and <section> are specific to .NET Framework 2.0 and 3.5. -->
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add /> elements, as demonstrated in the .NET Framework 4.0 - 4.8 sample code above. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

#### <a name="extend-programmatically-net-framework-net-core-net-50"></a><span data-ttu-id="e87c7-143">Programm gesteuertes erweitern (.NET Framework, .net Core, .net 5.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="e87c7-143">Extend programmatically (.NET Framework, .NET Core, .NET 5.0+)</span></span>

<span data-ttu-id="e87c7-144">Die Liste der zulässigen Typen kann auch Programm gesteuert erweitert werden, indem " [AppDomain. SetData](/dotnet/api/system.appdomain.setdata) " mit dem bekannten Schlüssel _System. Data. datasetdefaultallowedtypes_verwendet wird, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-144">The list of allowed types can also be extended programmatically by using [AppDomain.SetData](/dotnet/api/system.appdomain.setdata) with the well-known key _System.Data.DataSetDefaultAllowedTypes_, as shown in the following code.</span></span>

```cs
Type[] extraAllowedTypes = new Type[]
{
    typeof(Fabrikam.CustomType),
    typeof(Contoso.AdditionalCustomType)
};

AppDomain.CurrentDomain.SetData("System.Data.DataSetDefaultAllowedTypes", extraAllowedTypes);
```

<span data-ttu-id="e87c7-145">Wenn Sie den Erweiterungsmechanismus verwenden, muss der Wert, der dem Schlüssel _System. Data. datasetdefaultallowedtypes_ zugeordnet ist, vom Typ sein `Type[]` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-145">If using the extension mechanism, the value associated with the key _System.Data.DataSetDefaultAllowedTypes_ must be of type `Type[]`.</span></span>

<span data-ttu-id="e87c7-146">Auf .NET Framework kann die Liste der zulässigen Typen mit _App.config_ und erweitert werden `AppDomain.SetData` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-146">On .NET Framework, the list of allowed types may be extended both with _App.config_ and `AppDomain.SetData`.</span></span> <span data-ttu-id="e87c7-147">In diesem Fall `DataSet` können und `DataTable` ein Objekt als Teil der Daten deserialisiert werden, wenn der Typ in einer der beiden Listen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e87c7-147">In this case, `DataSet` and `DataTable` will allow an object to be deserialized as part of the data if its type is present in either list.</span></span>

### <a name="run-an-app-in-audit-mode-net-framework"></a><span data-ttu-id="e87c7-148">Ausführen einer APP im Überwachungsmodus (.NET Framework)</span><span class="sxs-lookup"><span data-stu-id="e87c7-148">Run an app in audit mode (.NET Framework)</span></span>

<span data-ttu-id="e87c7-149">In .NET Framework werden `DataSet` und `DataTable` eine Funktion für den Überwachungsmodus bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-149">In .NET Framework, `DataSet` and `DataTable` provide an audit mode capability.</span></span> <span data-ttu-id="e87c7-150">Wenn der Überwachungsmodus aktiviert ist, `DataSet` und `DataTable` vergleichen Sie die Typen eingehender Objekte mit der Liste der zulässigen Typen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-150">When audit mode is enabled, `DataSet` and `DataTable` compare the types of incoming objects against the allowed types list.</span></span> <span data-ttu-id="e87c7-151">Wenn jedoch ein Objekt, dessen Typ nicht zulässig ist, angezeigt wird, wird **keine** Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e87c7-151">However, if an object whose type is not allowed is seen, an exception is **not** thrown.</span></span> <span data-ttu-id="e87c7-152">`DataSet`Und `DataTable` Benachrichtigen alle angefügten `TraceListener` Instanzen, dass ein Verdächtiger Typ vorhanden ist, sodass `TraceListener` diese Informationen protokolliert werden können.</span><span class="sxs-lookup"><span data-stu-id="e87c7-152">Instead, `DataSet` and `DataTable` notify any attached `TraceListener` instances that a suspicious type is present, allowing the `TraceListener` to log this information.</span></span> <span data-ttu-id="e87c7-153">Es wird keine Ausnahme ausgelöst, und der Deserialisierungsvorgang wird fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-153">No exception is thrown and the deserialization operation continues.</span></span>

> [!WARNING]
> <span data-ttu-id="e87c7-154">Das Ausführen einer APP im Überwachungsmodus sollte nur ein temporäres Measure sein, das zum Testen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e87c7-154">Running an app in "audit mode" should only be a temporary measure used for testing.</span></span> <span data-ttu-id="e87c7-155">Wenn der Überwachungsmodus aktiviert ist `DataSet` , `DataTable` erzwingen und erzwingen keine Typeinschränkungen, wodurch eine Sicherheitslücke in der APP eingeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e87c7-155">When audit mode is enabled, `DataSet` and `DataTable` do not enforce type restrictions, which can introduce a security hole inside your app.</span></span> <span data-ttu-id="e87c7-156">Weitere Informationen finden Sie in den Abschnitten [Entfernen aller Typeinschränkungen](#ratr) und [Sicherheit in Bezug auf nicht vertrauenswürdige Eingaben](#swr).</span><span class="sxs-lookup"><span data-stu-id="e87c7-156">For more information, see the sections titled [Removing all type restrictions](#ratr) and [Safety with regard to untrusted input](#swr).</span></span>

<span data-ttu-id="e87c7-157">Der Überwachungsmodus kann über _App.config_aktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="e87c7-157">Audit mode can be enabled through _App.config_:</span></span>

* <span data-ttu-id="e87c7-158">Weitere Informationen über den richtigen Wert für das-Element finden Sie im Abschnitt [Erweitern der Konfiguration](#etc) in diesem Dokument `<configSections>` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-158">See the [Extending through configuration](#etc) section in this document for information on the proper value to put for the `<configSections>` element.</span></span>
* <span data-ttu-id="e87c7-159">Verwenden `<allowedTypes auditOnly="true">` Sie, um den Überwachungsmodus zu aktivieren, wie im folgenden Markup gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-159">Use `<allowedTypes auditOnly="true">` to enable audit mode, as shown in the following markup.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- See the section of this document titled "Extending through configuration" for the appropriate
         <sectionGroup> and <section> elements to put here, depending on whether you're running .NET
         Framework 2.0 - 3.5 or 4.0 - 4.8. -->
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes auditOnly="true"> <!-- setting auditOnly="true" enables audit mode -->
      <!-- Optional <add /> elements as needed. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

<span data-ttu-id="e87c7-160">Sobald der Überwachungsmodus aktiviert ist, können Sie _App.config_ verwenden, um eine Verbindung mit `TraceListener` dem `DataSet` integrierten `TraceSource.` Namen der integrierten Ablauf Verfolgungs Quelle herzustellen. _System.Data.DataSet_</span><span class="sxs-lookup"><span data-stu-id="e87c7-160">Once audit mode is enabled, you can use _App.config_ to connect your preferred `TraceListener` to the `DataSet` built-in `TraceSource.` The name of the built-in trace source is _System.Data.DataSet_.</span></span> <span data-ttu-id="e87c7-161">Im folgenden Beispiel wird veranschaulicht, wie Ablauf Verfolgungs Ereignisse in die Konsole _und_ in eine Protokolldatei auf dem Datenträger geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="e87c7-161">The following sample demonstrates writing trace events to the console _and_ to a log file on disk.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.Data.DataSet"
              switchType="System.Diagnostics.SourceSwitch"
              switchValue="Warning">
        <listeners>
          <!-- write to the console -->
          <add name="console"
               type="System.Diagnostics.ConsoleTraceListener" />
          <!-- *and* write to a log file on disk -->
          <add name="filelog"
               type="System.Diagnostics.TextWriterTraceListener"
               initializeData="c:\logs\mylog.txt" />
        </listeners>
      </source>
    </sources>
  </system.diagnostics>
</configuration>
```

<span data-ttu-id="e87c7-162">Weitere Informationen zu `TraceSource` und `TraceListener` finden Sie im Dokument Gewusst [wie: Verwenden von TraceSource und Filtern mit](/dotnet/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners)Ablaufverfolgungslistenern.</span><span class="sxs-lookup"><span data-stu-id="e87c7-162">For more information on `TraceSource` and `TraceListener`, see the document [How to: Use TraceSource and Filters with Trace Listeners](/dotnet/framework/debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners).</span></span>

<span data-ttu-id="e87c7-163">**Hinweis**: das Ausführen einer APP im Überwachungsmodus ist in .net Core oder .net 5,0 und höher nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e87c7-163">**Note**: Running an app in audit mode is not available in .NET Core or in .NET 5.0 and later.</span></span>

<a name="ratr"></a>

### <a name="remove-all-type-restrictions"></a><span data-ttu-id="e87c7-164">Alle Typeinschränkungen entfernen</span><span class="sxs-lookup"><span data-stu-id="e87c7-164">Remove all type restrictions</span></span>

<span data-ttu-id="e87c7-165">Wenn eine APP alle typeinschränkungs Einschränkungen von und entfernen muss `DataSet` `DataTable` :</span><span class="sxs-lookup"><span data-stu-id="e87c7-165">If an app must remove all type limiting restrictions from `DataSet` and `DataTable`:</span></span>

* <span data-ttu-id="e87c7-166">Es gibt mehrere Optionen, um typeinschränkungs Beschränkungen zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="e87c7-166">There are several options to suppress type limiting restrictions.</span></span>
* <span data-ttu-id="e87c7-167">Welche Optionen verfügbar sind, hängt vom Framework ab, auf das die APP abzielt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-167">The options available depend on the framework the app targets.</span></span>

> [!WARNING]
> <span data-ttu-id="e87c7-168">Wenn alle Typeinschränkungen entfernt werden, kann dies zu einer Sicherheitslücke in der APP führen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-168">Removing all type restrictions can introduce a security hole inside the app.</span></span> <span data-ttu-id="e87c7-169">Wenn Sie diesen Mechanismus verwenden, stellen Sie sicher, dass die APP **nicht** `DataSet` oder `DataTable` zum Lesen nicht vertrauenswürdiger Eingaben verwendet.</span><span class="sxs-lookup"><span data-stu-id="e87c7-169">When using this mechanism, ensure the app does **not** use `DataSet` or `DataTable` to read untrusted input.</span></span> <span data-ttu-id="e87c7-170">Weitere Informationen finden Sie unter [CVE-2020-1147](https://portal.msrc.microsoft.com/security-guidance/advisory/CVE-2020-1147) und im folgenden Abschnitt mit dem Titel [Sicherheit in Bezug auf nicht vertrauenswürdige Eingaben](#swr).</span><span class="sxs-lookup"><span data-stu-id="e87c7-170">For more information, see [CVE-2020-1147](https://portal.msrc.microsoft.com/security-guidance/advisory/CVE-2020-1147) and the following section titled [Safety with regard to untrusted input](#swr).</span></span>

#### <a name="through-appcontext-configuration-net-framework-46---48-net-core-21-and-later-net-50-and-later"></a><span data-ttu-id="e87c7-171">Über appContext-Konfiguration (.NET Framework 4,6-4,8, .net Core 2,1 und höher, .net 5,0 und höher)</span><span class="sxs-lookup"><span data-stu-id="e87c7-171">Through AppContext configuration (.NET Framework 4.6 - 4.8, .NET Core 2.1 and later, .NET 5.0 and later)</span></span>

<span data-ttu-id="e87c7-172">`AppContext`Wenn der Schalter `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` auf festgelegt ist, werden `true` alle typeinschränkungs Einschränkungen von `DataSet` und entfernt `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-172">The `AppContext` switch, `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation`, when set to `true` removes all type limiting restrictions from `DataSet` and `DataTable`.</span></span>

<span data-ttu-id="e87c7-173">In .NET Framework kann dieser Schalter über _App.config_aktiviert werden, wie in der folgenden Konfiguration gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e87c7-173">In .NET Framework, this switch can be enabled via _App.config_, as shown in the following configuration:</span></span>

```xml
<configuration>
   <runtime>
      <!-- Warning: setting the following switch can introduce a security problem. -->
      <AppContextSwitchOverrides value="Switch.System.Data.AllowArbitraryDataSetTypeInstantiation=true" />
   </runtime>
</configuration>
```

<span data-ttu-id="e87c7-174">In ASP.net ist das- `<AppContextSwitchOverrides>` Element nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e87c7-174">In ASP.NET, the `<AppContextSwitchOverrides>` element is not available.</span></span> <span data-ttu-id="e87c7-175">Stattdessen kann der Schalter über _Web.config_aktiviert werden, wie in der folgenden Konfiguration gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e87c7-175">Instead, the switch can be enabled via _Web.config_, as shown in the following configuration:</span></span>

```xml
<configuration>
    <appSettings>
        <!-- Warning: setting the following switch can introduce a security problem. -->
        <add key="AppContext.SetSwitch:Switch.System.Data.AllowArbitraryDataSetTypeInstantiation" value="true" />
    </appSettings>
</configuration>
```

<span data-ttu-id="e87c7-176">Weitere Informationen finden Sie unter dem- [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) Element.</span><span class="sxs-lookup"><span data-stu-id="e87c7-176">For more information, see the [\<AppContextSwitchOverrides>](/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) element.</span></span>

<span data-ttu-id="e87c7-177">In .net Core, .net 5 und ASP.net Core wird diese Einstellung durch _runtimeconfig.jsauf_gesteuert, wie im folgenden JSON-Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e87c7-177">In .NET Core, .NET 5, and ASP.NET Core, this setting is controlled by _runtimeconfig.json_, as shown in the following JSON:</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "Switch.System.Data.AllowArbitraryDataSetTypeInstantiation": true
    }
  }
}
```

<span data-ttu-id="e87c7-178">Weitere Informationen finden Sie unter ["Einstellungen für die .net Core-Laufzeitkonfiguration"](/dotnet/core/run-time-config/).</span><span class="sxs-lookup"><span data-stu-id="e87c7-178">For more information, see [".NET Core run-time configuration settings"](/dotnet/core/run-time-config/).</span></span>

<span data-ttu-id="e87c7-179">`AllowArbitraryDataSetTypeInstantiation`kann auch Programm gesteuert über [appContext. sezwitch](/dotnet/api/system.appcontext.setswitch) festgelegt werden, anstatt eine Konfigurationsdatei zu verwenden, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e87c7-179">`AllowArbitraryDataSetTypeInstantiation` can also be set programmatically via [AppContext.SetSwitch](/dotnet/api/system.appcontext.setswitch) instead of using a configuration file, as shown in the following code:</span></span>

```cs
// Warning: setting the following switch can introduce a security problem.
AppContext.SetSwitch("Switch.System.Data.AllowArbitraryDataSetTypeInstantiation", true);
```

 <span data-ttu-id="e87c7-180">Wenn Sie den vorhergehenden programmgesteuerten Ansatz auswählen, sollte der-Aufrufvorgang `AppContext.SetSwitch` früh beim Starten der app auftreten.</span><span class="sxs-lookup"><span data-stu-id="e87c7-180">If you choose the preceding programmatic approach, the call to `AppContext.SetSwitch` should occur early in the apps startup.</span></span>

#### <a name="through-the-machine-wide-registry-net-framework-20---48"></a><span data-ttu-id="e87c7-181">Über die Computer weite Registrierung (.NET Framework 2,0-4,8)</span><span class="sxs-lookup"><span data-stu-id="e87c7-181">Through the machine-wide registry (.NET Framework 2.0 - 4.8)</span></span>

<span data-ttu-id="e87c7-182">Wenn `AppContext` nicht verfügbar ist, können typeinschränkungs Überprüfungen mit der Windows-Registrierung deaktiviert werden:</span><span class="sxs-lookup"><span data-stu-id="e87c7-182">If `AppContext` is not available, type limiting checks can be disabled with the Windows registry:</span></span>

* <span data-ttu-id="e87c7-183">Ein Administrator muss die Registrierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e87c7-183">An administrator must configure the registry.</span></span>
* <span data-ttu-id="e87c7-184">Die Verwendung der Registrierung ist eine Computer weite Änderung und wirkt sich auf _alle_ Apps aus, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e87c7-184">Using the registry is a machine-wide change and will affect _all_ apps running on the machine.</span></span>

| <span data-ttu-id="e87c7-185">type</span><span class="sxs-lookup"><span data-stu-id="e87c7-185">Type</span></span>  |  <span data-ttu-id="e87c7-186">Wert</span><span class="sxs-lookup"><span data-stu-id="e87c7-186">Value</span></span> |
|---|---|
| <span data-ttu-id="e87c7-187">**Registrierungsschlüssel**</span><span class="sxs-lookup"><span data-stu-id="e87c7-187">**Registry key**</span></span> | `HKLM\SOFTWARE\Microsoft\.NETFramework\AppContext` |
| <span data-ttu-id="e87c7-188">**Wertname**</span><span class="sxs-lookup"><span data-stu-id="e87c7-188">**Value name**</span></span> | `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` |
| <span data-ttu-id="e87c7-189">**Werttyp**</span><span class="sxs-lookup"><span data-stu-id="e87c7-189">**Value type**</span></span> | `REG_SZ` |
| <span data-ttu-id="e87c7-190">**Wertdaten**</span><span class="sxs-lookup"><span data-stu-id="e87c7-190">**Value data**</span></span> | `true` |

<span data-ttu-id="e87c7-191">Bei einem 64-Bit-Betriebssystem muss dieser Wert, der sowohl für den 64-Bit-Schlüssel (oben gezeigt) als auch für den 32-Bit-Schlüssel hinzugefügt werden muss, hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e87c7-191">On a 64-bit operating system, this value my need to be added for both the 64-bit key (shown above) and the 32-bit key.</span></span> <span data-ttu-id="e87c7-192">Der 32-Bit-Schlüssel befindet sich unter `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-192">The 32-bit key is located at `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext`.</span></span>

<span data-ttu-id="e87c7-193">Weitere Informationen zum Verwenden der Registrierung zum Konfigurieren von `AppContext` finden Sie unter ["appContext für Bibliotheksconsumer"](/dotnet/api/system.appcontext#appcontext-for-library-consumers).</span><span class="sxs-lookup"><span data-stu-id="e87c7-193">For more information on using the registry to configure `AppContext`, see ["AppContext for library consumers"](/dotnet/api/system.appcontext#appcontext-for-library-consumers).</span></span>

<a name="swr"></a>

## <a name="safety-with-regard-to-untrusted-input"></a><span data-ttu-id="e87c7-194">Sicherheit in Bezug auf nicht vertrauenswürdige Eingaben</span><span class="sxs-lookup"><span data-stu-id="e87c7-194">Safety with regard to untrusted input</span></span>

<span data-ttu-id="e87c7-195">Während `DataSet` und `DataTable` erzwingen Standardbeschränkungen für die Typen, die während der Deserialisierung von XML-Nutzlasten vorhanden sein dürfen, __ `DataSet` und `DataTable` sind im Allgemeinen nicht sicher, wenn Sie mit nicht vertrauenswürdiger Eingabe__ aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="e87c7-195">While `DataSet` and `DataTable` do impose default limitations on the types that are allowed to be present while deserializing XML payloads, __`DataSet` and `DataTable` are in general not safe when populated with untrusted input.__</span></span> <span data-ttu-id="e87c7-196">Im folgenden finden Sie eine nicht vollständige Liste der Methoden, mit denen eine- `DataSet` oder- `DataTable` Instanz möglicherweise nicht vertrauenswürdige Eingaben liest.</span><span class="sxs-lookup"><span data-stu-id="e87c7-196">The following is a non-exhaustive list of ways that a `DataSet` or `DataTable` instance might read untrusted input.</span></span>

* <span data-ttu-id="e87c7-197">Ein `DataAdapter` verweist auf eine-Datenbank, und die- `DataAdapter.Fill` Methode wird verwendet, um eine `DataSet` mit dem Inhalt einer Datenbankabfrage aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-197">A `DataAdapter` references a database, and the `DataAdapter.Fill` method is used to populate a `DataSet` with the contents of a database query.</span></span>
* <span data-ttu-id="e87c7-198">Die `DataSet.ReadXml` -Methode oder die- `DataTable.ReadXml` Methode wird zum Lesen einer XML-Datei mit Spalten-und Zeilen Informationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="e87c7-198">The `DataSet.ReadXml` or `DataTable.ReadXml` method is used to read an XML file containing column and row information.</span></span>
* <span data-ttu-id="e87c7-199">Eine- `DataSet` oder- `DataTable` Instanz wird als Teil eines ASP.net (SOAP)-Webdiensts oder eines WCF-Endpunkts serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e87c7-199">A `DataSet` or `DataTable` instance is serialized as part of a ASP.NET (SOAP) web services or WCF endpoint.</span></span>
* <span data-ttu-id="e87c7-200">Ein Serialisierungsprogramm wie `XmlSerializer` wird verwendet, um eine- `DataSet` Instanz oder eine- `DataTable` Instanz aus einem XML-Stream zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="e87c7-200">A serializer such as `XmlSerializer` is used to deserialize a `DataSet` or `DataTable` instance from an XML stream.</span></span>
* <span data-ttu-id="e87c7-201">Ein Serialisierungsprogramm wie `JsonConvert` wird verwendet, um eine- `DataSet` Instanz oder eine- `DataTable` Instanz aus einem JSON-Stream zu deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="e87c7-201">A serializer such as `JsonConvert` is used to deserialize a `DataSet` or `DataTable` instance from a JSON stream.</span></span> <span data-ttu-id="e87c7-202">`JsonConvert`ist eine Methode im beliebten Drittanbieter- [Newtonsoft.Jsfür](https://www.newtonsoft.com/json) die-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="e87c7-202">`JsonConvert` is a method in the popular third-party [Newtonsoft.Json](https://www.newtonsoft.com/json) library.</span></span>
* <span data-ttu-id="e87c7-203">Ein Serialisierungsprogramm wie `BinaryFormatter` wird zum Deserialisieren einer- `DataSet` oder- `DataTable` Instanz aus einem Rohdaten Strom verwendet.</span><span class="sxs-lookup"><span data-stu-id="e87c7-203">A serializer such as `BinaryFormatter` is used to deserialize a `DataSet` or `DataTable` instance from a raw byte stream.</span></span>

<span data-ttu-id="e87c7-204">In diesem Dokument werden die Sicherheitsüberlegungen für die vorangegangenen Szenarien erläutert.</span><span class="sxs-lookup"><span data-stu-id="e87c7-204">This document discusses safety considerations for the preceding scenarios.</span></span>

## <a name="use-dataadapterfill-to-populate-a-dataset-from-an-untrusted-data-source"></a><span data-ttu-id="e87c7-205">Verwenden `DataAdapter.Fill` zum Auffüllen eines `DataSet` aus einer nicht vertrauenswürdigen Datenquelle</span><span class="sxs-lookup"><span data-stu-id="e87c7-205">Use `DataAdapter.Fill` to populate a `DataSet` from an untrusted data source</span></span>

<span data-ttu-id="e87c7-206">Eine- `DataSet` Instanz kann mithilfe der-Methode aus einem ausgefüllt werden `DataAdapter` , wie im folgenden Beispiel gezeigt. [ `DataAdapter.Fill` ](/dotnet/api/system.data.common.dataadapter.fill)</span><span class="sxs-lookup"><span data-stu-id="e87c7-206">A `DataSet` instance can be populated from a `DataAdapter` by using [the `DataAdapter.Fill` method](/dotnet/api/system.data.common.dataadapter.fill), as shown in the following example.</span></span>

```cs
// Assumes that connection is a valid SqlConnection object.  
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";  
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");
```

<span data-ttu-id="e87c7-207">(Das obige Codebeispiel ist Teil eines größeren Beispiels, das beim Auffüllen [eines Datasets von einem DataAdapter](/dotnet/framework/data/adonet/populating-a-dataset-from-a-dataadapter)-Element enthalten ist.)</span><span class="sxs-lookup"><span data-stu-id="e87c7-207">(The code sample above is part of a larger sample found at [Populating a DataSet from a DataAdapter](/dotnet/framework/data/adonet/populating-a-dataset-from-a-dataadapter).)</span></span>

> <span data-ttu-id="e87c7-208">Die meisten apps können vereinfachen und davon ausgehen, dass Ihre Datenbankebene vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="e87c7-208">Most apps can simplify and assume that their database layer is trusted.</span></span> <span data-ttu-id="e87c7-209">Wenn Sie jedoch eine [Bedrohungsmodellierung](https://www.microsoft.com/securityengineering/sdl/threatmodeling) für Ihre apps durchlaufen, kann Ihr Bedrohungs Modell davon abweichen, dass es eine Vertrauens Grenze zwischen der Anwendung (Client) und der Datenbankschicht (Server) gibt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-209">However, if you are in the habit of [threat modeling](https://www.microsoft.com/securityengineering/sdl/threatmodeling) your apps, your threat model may consider there to be a trust boundary between the application (client) and database layer (server).</span></span> <span data-ttu-id="e87c7-210">Die Verwendung der [gegenseitigen Authentifizierung](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) oder der [Aad-Authentifizierung](/azure/azure-sql/database/authentication-aad-overview) zwischen Client und Server ist eine Möglichkeit, um die Risiken zu beheben, die mit diesem verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="e87c7-210">Using [mutual authentication](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) or [AAD authentication](/azure/azure-sql/database/authentication-aad-overview) between client and server is one way to help address the risks associated with this.</span></span> <span data-ttu-id="e87c7-211">Im restlichen Teil dieses Abschnitts wird das mögliche Ergebnis eines Clients erläutert, der eine Verbindung mit einem nicht vertrauenswürdigen Server herstellt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-211">The remainder of this section discusses the possible result of a client connecting to an untrusted server.</span></span>

<span data-ttu-id="e87c7-212">Die Auswirkungen, die auf eine `DataAdapter` nicht vertrauenswürdige Datenquelle verweisen, hängen von der Implementierung der `DataAdapter` selbst ab.</span><span class="sxs-lookup"><span data-stu-id="e87c7-212">The consequences of pointing a `DataAdapter` at an untrusted data source depend on the implementation of the `DataAdapter` itself.</span></span>

### <a name="sqldataadapter"></a><span data-ttu-id="e87c7-213">SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="e87c7-213">SqlDataAdapter</span></span>

<span data-ttu-id="e87c7-214">Für den integrierten Typ [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter)könnte das verweisen auf eine nicht vertrauenswürdige Datenquelle zu einem Denial-of-Service-Angriff (DOS) führen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-214">For the built-in type [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter), referencing an untrusted data source could result in a denial of service (DoS) attack.</span></span> <span data-ttu-id="e87c7-215">Der DOS-Angriff könnte dazu führen, dass die APP nicht mehr reagiert oder abgestürzt wird.</span><span class="sxs-lookup"><span data-stu-id="e87c7-215">The DoS attack could result in the app becoming unresponsive or crashing.</span></span> <span data-ttu-id="e87c7-216">Wenn ein Angreifer eine DLL neben der APP zusammenstellen kann, kann er möglicherweise auch eine lokale Codeausführung erreichen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-216">If an attacker can plant a DLL alongside the app, they may also be able to achieve local code execution.</span></span>

### <a name="other-dataadapter-types"></a><span data-ttu-id="e87c7-217">Andere DataAdapter-Typen</span><span class="sxs-lookup"><span data-stu-id="e87c7-217">Other DataAdapter types</span></span>

<span data-ttu-id="e87c7-218">`DataAdapter`Implementierungen von Drittanbietern müssen eigene Bewertungen darüber treffen, welche Sicherheitsgarantien Sie bei nicht vertrauenswürdigen Eingaben bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-218">Third-party `DataAdapter` implementations must make their own assessments about what security guarantees they provide in the face of untrusted inputs.</span></span> <span data-ttu-id="e87c7-219">.Net kann für diese Implementierungen keinerlei Sicherheitsgarantien treffen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-219">.NET cannot make any safety guarantees regarding these implementations.</span></span>

<a name="dsrdtr"></a>

## <a name="datasetreadxml-and-datatablereadxml"></a><span data-ttu-id="e87c7-220">DataSet. Read XML und databel. Read XML</span><span class="sxs-lookup"><span data-stu-id="e87c7-220">DataSet.ReadXml and DataTable.ReadXml</span></span>

<span data-ttu-id="e87c7-221">Die `DataSet.ReadXml` -Methode und die- `DataTable.ReadXml` Methode sind bei Verwendung mit nicht vertrauenswürdigen Eingaben nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="e87c7-221">The `DataSet.ReadXml` and `DataTable.ReadXml` methods are not safe when used with untrusted input.</span></span> <span data-ttu-id="e87c7-222">Es wird dringend empfohlen, dass Consumer stattdessen eine der alternativen verwenden, die weiter unten in diesem Dokument beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="e87c7-222">We strongly recommend that consumers instead consider using one of the alternatives outlined later in this document.</span></span>

<span data-ttu-id="e87c7-223">Die Implementierungen von `DataSet.ReadXml` und `DataTable.ReadXml` wurden ursprünglich erstellt, bevor die Sicherheitsrisiken der Serialisierung eine gut verständliche Bedrohungs Kategorie waren.</span><span class="sxs-lookup"><span data-stu-id="e87c7-223">The implementations of `DataSet.ReadXml` and `DataTable.ReadXml` were originally created before serialization vulnerabilities were a well-understood threat category.</span></span> <span data-ttu-id="e87c7-224">Folglich befolgt der Code die aktuellen bewährten Sicherheitsmethoden nicht.</span><span class="sxs-lookup"><span data-stu-id="e87c7-224">As a result, the code does not follow current security best practices.</span></span> <span data-ttu-id="e87c7-225">Diese APIs können als Vektoren für Angreifer verwendet werden, um DOS-Angriffe auf Web-Apps auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-225">These APIs can be used as vectors for attackers to perform DoS attacks against web apps.</span></span> <span data-ttu-id="e87c7-226">Diese Angriffe können dazu führen, dass der Webdienst nicht reagiert oder zu unerwartetem Prozess Abbruch führt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-226">These attacks might render the web service unresponsive or result in unexpected process termination.</span></span> <span data-ttu-id="e87c7-227">Das Framework bietet keine entschärfungen für diese Angriffs Kategorien, und .net betrachtet dieses Verhalten "Entwurfs bedingt".</span><span class="sxs-lookup"><span data-stu-id="e87c7-227">The framework does not provide mitigations for these attack categories and .NET considers this behavior "by design".</span></span>

<span data-ttu-id="e87c7-228">.Net hat Sicherheitsupdates veröffentlicht, um einige Probleme zu beheben, wie z. b. Offenlegung von Informationen oder Remote Codeausführung in `DataSet.ReadXml` und `DataTable.ReadXml` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-228">.NET has released security updates to mitigate some issues such as information disclosure or remote code execution in `DataSet.ReadXml` and `DataTable.ReadXml`.</span></span> <span data-ttu-id="e87c7-229">Die .net-Sicherheitsupdates bieten möglicherweise keinen umfassenden Schutz gegen diese Bedrohungs Kategorien.</span><span class="sxs-lookup"><span data-stu-id="e87c7-229">The .NET security updates may not provide complete protection against these threat categories.</span></span> <span data-ttu-id="e87c7-230">Consumer sollten ihre einzelnen Szenarios bewerten und ihre potenzielle Gefahr für diese Risiken berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-230">Consumers should assess their individual scenarios and consider their potential exposure to these risks.</span></span>

<span data-ttu-id="e87c7-231">Consumer sollten beachten, dass sich Sicherheitsupdates für diese APIs in einigen Situationen auf die Anwendungs Kompatibilität auswirken können.</span><span class="sxs-lookup"><span data-stu-id="e87c7-231">Consumers should be aware that security updates to these APIs may impact application compatibility in some situations.</span></span> <span data-ttu-id="e87c7-232">Außerdem besteht die Möglichkeit, dass eine neue Sicherheitslücke in diesen APIs erkannt wird, für die .net nicht praktisch ein Sicherheitsupdate veröffentlichen kann.</span><span class="sxs-lookup"><span data-stu-id="e87c7-232">Furthermore, the possibility exists that a novel vulnerability in these APIs will be discovered for which .NET can't practically publish a security update.</span></span>

<span data-ttu-id="e87c7-233">Es wird empfohlen, dass die folgenden APIs für Consumer der folgenden APIs:</span><span class="sxs-lookup"><span data-stu-id="e87c7-233">We recommend that consumers of these APIs either:</span></span>

* <span data-ttu-id="e87c7-234">Sie sollten eine der alternativen verwenden, die weiter unten in diesem Dokument beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="e87c7-234">Consider using one of the alternatives outlined later in this document.</span></span>
* <span data-ttu-id="e87c7-235">Führen Sie einzelne Risikobewertungen für Ihre apps durch.</span><span class="sxs-lookup"><span data-stu-id="e87c7-235">Perform individual risk assessments on their apps.</span></span>

<span data-ttu-id="e87c7-236">Es ist die alleinige Verantwortung des Consumers, zu bestimmen, ob diese APIs verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-236">It is the consumer's sole responsibility to determine whether to utilize these APIs.</span></span> <span data-ttu-id="e87c7-237">Consumer sollten alle Sicherheits-, technischen und rechtlichen Risiken, einschließlich gesetzlicher Anforderungen, bewerten, die möglicherweise mit diesen APIs einhergehen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-237">Consumers should assess any security, technical, and legal risks, including regulatory requirements, that may accompany using these APIs.</span></span>

## <a name="dataset-and-datatable-via-aspnet-web-services-or-wcf"></a><span data-ttu-id="e87c7-238">DataSet und Datentabelle über ASP.NET-Webdienste oder WCF</span><span class="sxs-lookup"><span data-stu-id="e87c7-238">DataSet and DataTable via ASP.NET web services or WCF</span></span>

<span data-ttu-id="e87c7-239">Es ist möglich, eine- `DataSet` oder eine- `DataTable` Instanz in einem ASP.net (SOAP)-Webdienst zu akzeptieren, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e87c7-239">It is possible to accept a `DataSet` or a `DataTable` instance in an ASP.NET (SOAP) web service, as demonstrated in the following code:</span></span>

```cs
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(DataTable dataTable)
    {
        /* Web method implementation. */
    }
}
```

<span data-ttu-id="e87c7-240">Eine Variation hierfür besteht nicht darin, `DataSet` oder `DataTable` direkt als Parameter zu akzeptieren, sondern stattdessen als Teil des gesamten SOAP-serialisierten Objekt Diagramms zu akzeptieren, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e87c7-240">A variation on this is not to accept `DataSet` or `DataTable` directly as a parameter, but instead to accept it as part of the overall SOAP serialized object graph, as shown in the following code:</span></span>

```cs
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(MyClass data)
    {
        /* Web method implementation. */
    }
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="e87c7-241">Oder verwenden Sie WCF anstelle von ASP.NET-Webdiensten:</span><span class="sxs-lookup"><span data-stu-id="e87c7-241">Or, using WCF instead of ASP.NET web services:</span></span>

```cs
using System.Data;
using System.ServiceModel;

[ServiceContract(Namespace = "http://contoso.com/")]
public interface IMyContract
{
    [OperationContract]
    string MyMethod(DataTable dataTable);
    [OperationContract]
    string MyOtherMethod(MyClass data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="e87c7-242">In all diesen Fällen sind das Bedrohungs Modell und die Sicherheitsgarantien mit dem [Abschnitt DataSet. Read XML und datbare. Read XML](#dsrdtr)identisch.</span><span class="sxs-lookup"><span data-stu-id="e87c7-242">In all of these cases, the threat model and security guarantees are the same as the [DataSet.ReadXml and DataTable.ReadXml section](#dsrdtr).</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-xmlserializer"></a><span data-ttu-id="e87c7-243">Deserialisieren eines Datasets oder einer Datentabelle über XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="e87c7-243">Deserialize a DataSet or DataTable via XmlSerializer</span></span>

<span data-ttu-id="e87c7-244">Entwickler können verwenden, `XmlSerializer` um `DataSet` -und-Instanzen zu deserialisieren `DataTable` , wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e87c7-244">Developers can use `XmlSerializer` to deserialize `DataSet` and `DataTable` instances, as shown in the following code:</span></span>

```cs
using System.Data;
using System.IO;
using System.Xml.Serialization;

public DataSet PerformDeserialization1(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(DataSet));
    return (DataSet)serializer.Deserialize(stream);
}

public MyClass PerformDeserialization2(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(MyClass));
    return (MyClass)serializer.Deserialize(stream);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="e87c7-245">In diesen Fällen sind das Bedrohungs Modell und die Sicherheitsgarantien mit dem [Abschnitt "DataSet. Read XML" und "datbare. Read XML](#dsrdtr) " identisch.</span><span class="sxs-lookup"><span data-stu-id="e87c7-245">In these cases, the threat model and security guarantees are the same as the [DataSet.ReadXml and DataTable.ReadXml section](#dsrdtr)</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-jsonconvert"></a><span data-ttu-id="e87c7-246">Deserialisieren eines Datasets oder einer Datentabelle über JsonConvert</span><span class="sxs-lookup"><span data-stu-id="e87c7-246">Deserialize a DataSet or DataTable via JsonConvert</span></span>

<span data-ttu-id="e87c7-247">Die beliebte newtonsoft [-Bibliothek von](https://www.newtonsoft.com/json) Drittanbietern kann verwendet werden `DataSet` , um-und-Instanzen zu deserialisieren `DataTable` , wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="e87c7-247">The popular third-party Newtonsoft library [JSON.NET](https://www.newtonsoft.com/json) can be used to deserialize `DataSet` and `DataTable` instances, as shown in the following code:</span></span>

```cs
using System.Data;
using Newtonsoft.Json;

public DataSet PerformDeserialization1(string json) {
    return JsonConvert.DeserializeObect<DataSet>(data);
}

public MyClass PerformDeserialization2(string json) {
    return JsonConvert.DeserializeObect<MyClass>(data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="e87c7-248">Das Deserialisieren `DataSet` `DataTable` von oder auf diese Weise aus einem nicht vertrauenswürdigen JSON-BLOB ist nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="e87c7-248">Deserializing a `DataSet` or `DataTable` in this manner from an untrusted JSON blob is not safe.</span></span> <span data-ttu-id="e87c7-249">Dieses Muster ist anfällig für einen Denial-of-Service-Angriff.</span><span class="sxs-lookup"><span data-stu-id="e87c7-249">This pattern is vulnerable to a denial of service attack.</span></span> <span data-ttu-id="e87c7-250">Ein solcher Angriff könnte die APP abstürzen oder nicht mehr reagiert.</span><span class="sxs-lookup"><span data-stu-id="e87c7-250">Such an attack could crash the app or render it unresponsive.</span></span>

<span data-ttu-id="e87c7-251">**Hinweis**: Microsoft kann die Implementierung von Bibliotheken von Drittanbietern, wie _Newtonsoft.Jsauf_, nicht rechtfertigen oder unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-251">**Note**: Microsoft does not warrant or support the implementation of third-party libraries like _Newtonsoft.Json_.</span></span> <span data-ttu-id="e87c7-252">Diese Informationen werden aus Gründen der Vollständigkeit bereitgestellt und sind zum Zeitpunkt der Erstellung dieses Artikels genau.</span><span class="sxs-lookup"><span data-stu-id="e87c7-252">This information is provided for completeness and is accurate as of the time of this writing.</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-binaryformatter"></a><span data-ttu-id="e87c7-253">Deserialisieren eines Datasets oder einer Datentabelle über BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="e87c7-253">Deserialize a DataSet or DataTable via BinaryFormatter</span></span>

<span data-ttu-id="e87c7-254">Entwickler dürfen niemals `BinaryFormatter` , `NetDataContractSerializer` , `SoapFormatter` oder verwandte ***unsichere*** Formatierer verwenden, um eine-oder- `DataSet` `DataTable` Instanz aus einer nicht vertrauenswürdigen Nutzlast zu deserialisieren:</span><span class="sxs-lookup"><span data-stu-id="e87c7-254">Developers must never use `BinaryFormatter`, `NetDataContractSerializer`, `SoapFormatter`, or related ***unsafe*** formatters to deserialize a `DataSet` or `DataTable` instance from an untrusted payload:</span></span>

* <span data-ttu-id="e87c7-255">Dies ist anfällig für einen vollständigen Remote Code Ausführungs Angriff.</span><span class="sxs-lookup"><span data-stu-id="e87c7-255">This is susceptible to a full remote code execution attack.</span></span>
* <span data-ttu-id="e87c7-256">Die Verwendung eines benutzerdefinierten `SerializationBinder` ist nicht ausreichend, um solche Angriffe zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="e87c7-256">Using a custom `SerializationBinder` is not sufficient to prevent such an attack.</span></span>

## <a name="safe-replacements"></a><span data-ttu-id="e87c7-257">Sichere Ersetzung</span><span class="sxs-lookup"><span data-stu-id="e87c7-257">Safe replacements</span></span>

<span data-ttu-id="e87c7-258">Für apps, die Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="e87c7-258">For apps that either:</span></span>

* <span data-ttu-id="e87c7-259">Akzeptieren Sie `DataSet` oder `DataTable` über einen ASMX-SOAP-Endpunkt oder einen WCF-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="e87c7-259">Accept `DataSet` or `DataTable` through an .asmx SOAP endpoint or a WCF endpoint.</span></span>
* <span data-ttu-id="e87c7-260">Deserialisieren nicht vertrauenswürdiger Daten in eine Instanz von `DataSet` oder `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="e87c7-260">Deserialize untrusted data into an instance of `DataSet` or `DataTable`.</span></span>

<span data-ttu-id="e87c7-261">Ersetzen Sie ggf. das Objektmodell, um [Entity Framework](/ef)zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e87c7-261">Consider replacing the object model to use [Entity Framework](/ef).</span></span> <span data-ttu-id="e87c7-262">Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="e87c7-262">Entity Framework:</span></span>

* <span data-ttu-id="e87c7-263">Ist ein Funktions Reiches, modernes, objektorientiertes Framework, das relationale Daten darstellen kann.</span><span class="sxs-lookup"><span data-stu-id="e87c7-263">Is a rich, modern, object-oriented framework that can represent relational data.</span></span>
* <span data-ttu-id="e87c7-264">Bietet [ein vielfältige Ökosystem](/ef/core/providers/) von Datenbankanbietern, damit Sie Datenbankabfragen über Ihre Entity Framework-Objekt Modelle problemlos projizieren können.</span><span class="sxs-lookup"><span data-stu-id="e87c7-264">Brings [a diverse ecosystem](/ef/core/providers/) of database providers to make it easy to project database queries via your Entity Framework object models.</span></span>
* <span data-ttu-id="e87c7-265">Bietet integrierte Schutzmaßnahmen beim Deserialisieren von Daten aus nicht vertrauenswürdigen Quellen.</span><span class="sxs-lookup"><span data-stu-id="e87c7-265">Offers built-in protections when deserializing data from untrusted sources.</span></span>

<span data-ttu-id="e87c7-266">Für apps, die `.aspx` SOAP-Endpunkte verwenden, sollten Sie diese Endpunkte für die Verwendung von [WCF](/dotnet/framework/wcf/)ändern.</span><span class="sxs-lookup"><span data-stu-id="e87c7-266">For apps that use `.aspx` SOAP endpoints, consider changing those endpoints to use [WCF](/dotnet/framework/wcf/).</span></span> <span data-ttu-id="e87c7-267">WCF ist ein vollständig erstellteren Austausch für `.asmx` Webdienste.</span><span class="sxs-lookup"><span data-stu-id="e87c7-267">WCF is a more fully featured replacement for `.asmx` web services.</span></span> <span data-ttu-id="e87c7-268">WCF-Endpunkte [können über SOAP](/dotnet/framework/wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients) zur Kompatibilität mit vorhandenen Aufrufern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="e87c7-268">WCF endpoints [can be exposed via SOAP](/dotnet/framework/wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients) for compatibility with existing callers.</span></span>
