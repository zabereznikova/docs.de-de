---
title: 'Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource'
ms.custom: 
ms.date: 04/10/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 96dd3f0a3ed27a9e09c62f3ad4f450ced5a8e644
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="1ee85-102">Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource</span><span class="sxs-lookup"><span data-stu-id="1ee85-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="1ee85-103">Häufig eine Zeitzone-fähige Anwendung erfordert das Vorhandensein einer bestimmten Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="1ee85-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="1ee85-104">Jedoch, da die Verfügbarkeit einzelner <xref:System.TimeZoneInfo> -Objekten hängt von Informationen, die in der Registrierung des lokalen Systems gespeichert, selbst normalerweise verfügbaren Zeitzonen möglicherweise nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1ee85-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="1ee85-105">Darüber hinaus Informationen über benutzerdefinierte Zeitzonen instanziiert, indem die <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode ist nicht mit anderen Informationen zur Zeitzone in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1ee85-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="1ee85-106">Um sicherzustellen, dass diese Zeitzonen verfügbar sind, wenn sie benötigt werden, können Sie speichern, indem sie serialisieren und diese später wiederherstellen, indem sie deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="1ee85-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="1ee85-107">In der Regel Serialisieren einer <xref:System.TimeZoneInfo> Objekt tritt auf, abgesehen von der Zeitzone-fähigen Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1ee85-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="1ee85-108">Abhängig von der Datenspeicher verwendet, um serialisierte halten <xref:System.TimeZoneInfo> Objekte Zeitzonendaten serialisiert werden können, im Rahmen einer Routine Einrichtung oder Installation (z. B., wenn die Daten in einen Anwendungsschlüssel der Registrierung gespeichert ist) oder als Teil einer Hilfsprogramm-Routine, die ausgeführt wird vor der endgültige Anwendung kompiliert wird, (z. B. wenn die serialisierten Daten in einer .NET XML-Ressourcendatei (.resx) gespeichert ist).</span><span class="sxs-lookup"><span data-stu-id="1ee85-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="1ee85-109">Zusätzlich zu einer Ressourcendatei, die mit der Anwendung kompiliert wird, können andere Datenspeicher für die Zeitzoneninformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ee85-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="1ee85-110">Hierzu gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1ee85-110">These include the following:</span></span>

* <span data-ttu-id="1ee85-111">Die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="1ee85-111">The registry.</span></span> <span data-ttu-id="1ee85-112">Beachten Sie, dass eine Anwendung der Unterschlüssel des Anwendungsschlüssel seines eigenen verwenden soll, um benutzerdefinierte Zeitzonendaten, anstatt die Unterschlüssel HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zonen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1ee85-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

* <span data-ttu-id="1ee85-113">Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="1ee85-113">Configuration files.</span></span>

* <span data-ttu-id="1ee85-114">Andere Systemdateien.</span><span class="sxs-lookup"><span data-stu-id="1ee85-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="1ee85-115">Um eine Zeitzone durch eine Serialisierung in eine RESX-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1ee85-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="1ee85-116">Abzurufen Sie eine vorhandene Zeitzone, oder erstellen Sie eine neue Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="1ee85-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="1ee85-117">Um eine vorhandene Zeitzone abzurufen, finden Sie unter [Vorgehensweise: Zugreifen auf die vordefinierte UTC und Ortszeit Zonenobjekte](../../../docs/standard/datetime/access-utc-and-local.md) und [wie: Instanziieren eines TimeZoneInfo-Objekts](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span><span class="sxs-lookup"><span data-stu-id="1ee85-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](../../../docs/standard/datetime/access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](../../../docs/standard/datetime/instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="1ee85-118">Um eine neue Zeitzone zu erstellen, rufen Sie eine der Überladungen der der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="1ee85-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="1ee85-119">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Zeitzonen ohne Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) und [Vorgehensweise: Erstellen von Zeitzonen mit Anpassungsregeln](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="1ee85-119">For more information, see [How to: Create time zones without adjustment rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="1ee85-120">Rufen Sie die <xref:System.TimeZoneInfo.ToSerializedString%2A> Methode, um eine Zeichenfolge zu erstellen, das die Zeitzone Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="1ee85-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="1ee85-121">Instanziieren einer <xref:System.IO.StreamWriter> Objekt, indem Sie den Namen und optional den Pfad der RESX-Datei, die die <xref:System.IO.StreamWriter> Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="1ee85-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="1ee85-122">Instanziieren einer <xref:System.Resources.ResXResourceWriter> -Objekt durch Übergeben der <xref:System.IO.StreamWriter> -Objekt an die <xref:System.Resources.ResXResourceWriter> Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="1ee85-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="1ee85-123">Übergeben der Zeitzone serialisierte Zeichenfolge an die <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="1ee85-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="1ee85-124">Rufen Sie die <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="1ee85-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="1ee85-125">Rufen Sie die <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="1ee85-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="1ee85-126">Schließen der <xref:System.IO.StreamWriter> Objekt durch Aufrufen seiner <xref:System.IO.StreamWriter.Close%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="1ee85-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="1ee85-127">Die Anwendung von Visual Studio-Projekt die generierte RESX-Datei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1ee85-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="1ee85-128">Mithilfe der **Eigenschaften** Fenster in Visual Studio verwenden, stellen sicher, dass der RESX-Datei **Buildvorgang** -Eigenschaftensatz auf **eingebettete Ressource**.</span><span class="sxs-lookup"><span data-stu-id="1ee85-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource**.</span></span>

## <a name="example"></a><span data-ttu-id="1ee85-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ee85-129">Example</span></span>

<span data-ttu-id="1ee85-130">Im folgenden Beispiel wird eine <xref:System.TimeZoneInfo> Objekt, das Central Normalzeit darstellt und ein <xref:System.TimeZoneInfo> Objekt, das zu einer .NET XML-Ressourcendatei mit dem Namen SerializedTimeZones.resx der Palmer Station, Antarktis Zeit darstellt.</span><span class="sxs-lookup"><span data-stu-id="1ee85-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="1ee85-131">Central Normalzeit ist in der Regel in der Registrierung definiert. Palmer Station, Antarktis ist eine benutzerdefinierte Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="1ee85-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="1ee85-132">In diesem Beispiel serialisiert <xref:System.TimeZoneInfo> -Objekten, die sie zum Zeitpunkt der Kompilierung in einer Ressourcendatei verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1ee85-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="1ee85-133">Da die <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> Methode fügt vollständige Header-Informationen zu einer .NET XML-Ressourcendatei, die nicht zum Hinzufügen von Ressourcen zu einer vorhandenen Datei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ee85-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="1ee85-134">Im Beispiel mit der Überprüfung der Datei SerializedTimeZones.resx behandelt und, falls vorhanden, speichern alle Ressourcen außer die beiden serialisiert Zeitzonen auf einen allgemeinen <xref:System.Collections.Generic.Dictionary%602> Objekt.</span><span class="sxs-lookup"><span data-stu-id="1ee85-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="1ee85-135">Die vorhandene Datei wird dann gelöscht, und vorhandenen Ressourcen werden in eine neue SerializedTimeZones.resx-Datei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1ee85-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="1ee85-136">Diese Datei werden auch der serialisierten Zeitzonendaten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1ee85-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="1ee85-137">Der Schlüssel (oder **Namen**) von Ressourcen sollten keine eingebettete Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1ee85-137">The key (or **Name**) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="1ee85-138">Die <xref:System.String.Replace%28System.String%2CSystem.String%29> Methode wird aufgerufen, um alle eingebetteten Leerzeichen in der Zeitzonenbezeichner zu entfernen, bevor sie die Ressourcendatei zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="1ee85-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="1ee85-139">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1ee85-139">Compiling the code</span></span>

<span data-ttu-id="1ee85-140">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1ee85-140">This example requires:</span></span>

* <span data-ttu-id="1ee85-141">Dem Projekt ein Verweis auf System.Windows.Forms.dll und "System.Core.dll" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1ee85-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="1ee85-142">Dass die folgenden Namespaces importiert werden:</span><span class="sxs-lookup"><span data-stu-id="1ee85-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="1ee85-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ee85-143">See also</span></span>

<span data-ttu-id="1ee85-144">[Datumsangaben, Uhrzeiten und Zeitzonen](../../../docs/standard/datetime/index.md)
[Übersicht über Zeitzonen](../../../docs/standard/datetime/time-zone-overview.md)
[Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="1ee85-144">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Time zone overview](../../../docs/standard/datetime/time-zone-overview.md)
[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span></span>
