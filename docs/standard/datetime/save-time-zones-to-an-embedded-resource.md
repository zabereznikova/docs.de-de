---
title: 'Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], saving
- time zone objects [.NET], serializing
- time zone objects [.NET], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
ms.openlocfilehash: 3d355003b3e6309644fa1ccaf779b2e63b0523d2
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063403"
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a><span data-ttu-id="92ff1-102">Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource</span><span class="sxs-lookup"><span data-stu-id="92ff1-102">How to: Save time zones to an embedded resource</span></span>

<span data-ttu-id="92ff1-103">Bei einer Zeit Zonen fähigen Anwendung ist es häufig erforderlich, dass eine bestimmte Zeitzone vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="92ff1-103">A time zone-aware application often requires the presence of a particular time zone.</span></span> <span data-ttu-id="92ff1-104">Da die Verfügbarkeit einzelner Objekte jedoch von <xref:System.TimeZoneInfo> Informationen abhängig ist, die in der Registrierung des lokalen Systems gespeichert sind, sind möglicherweise auch für die Kunden verfügbare Zeitzonen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="92ff1-104">However, because the availability of individual <xref:System.TimeZoneInfo> objects depends on information stored in the local system's registry, even customarily available time zones may be absent.</span></span> <span data-ttu-id="92ff1-105">Außerdem werden Informationen über benutzerdefinierte Zeitzonen, die mithilfe der-Methode instanziiert werden, <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> nicht mit anderen Zeitzoneninformationen in der Registrierung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="92ff1-105">In addition, information about custom time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method is not stored with other time zone information in the registry.</span></span> <span data-ttu-id="92ff1-106">Um sicherzustellen, dass diese Zeitzonen bei Bedarf verfügbar sind, können Sie Sie durch serialisieren speichern und später wiederherstellen, indem Sie Sie deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="92ff1-106">To ensure that these time zones are available when they are needed, you can save them by serializing them, and later restore them by deserializing them.</span></span>

<span data-ttu-id="92ff1-107">In der Regel erfolgt die Serialisierung eines- <xref:System.TimeZoneInfo> Objekts von der Zeit Zonen fähigen Anwendung.</span><span class="sxs-lookup"><span data-stu-id="92ff1-107">Typically, serializing a <xref:System.TimeZoneInfo> object occurs apart from the time zone-aware application.</span></span> <span data-ttu-id="92ff1-108">Abhängig vom Datenspeicher, der für serialisierte Objekte verwendet wird <xref:System.TimeZoneInfo> , Zeit Zonendaten können als Teil einer Setup-oder Installationsroutine (z. b. wenn die Daten in einem Anwendungs Schlüssel der Registrierung gespeichert sind) oder als Teil einer hilfsprogrammroutine serialisiert werden, die vor der Kompilierung der endgültigen Anwendung ausgeführt wird (z. b. wenn die serialisierten Daten in einer .NET-XML-Ressourcen Datei (. resx) gespeichert sind).</span><span class="sxs-lookup"><span data-stu-id="92ff1-108">Depending on the data store used to hold serialized <xref:System.TimeZoneInfo> objects, time zone data may be serialized as part of a setup or installation routine (for example, when the data is stored in an application key of the registry), or as part of a utility routine that runs before the final application is compiled (for example, when the serialized data is stored in a .NET XML resource (.resx) file).</span></span>

<span data-ttu-id="92ff1-109">Zusätzlich zu einer Ressourcen Datei, die mit der Anwendung kompiliert wird, können auch mehrere andere Datenspeicher für Zeitzoneninformationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="92ff1-109">In addition to a resource file that is compiled with the application, several other data stores can be used for time zone information.</span></span> <span data-ttu-id="92ff1-110">Hierzu gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="92ff1-110">These include the following:</span></span>

- <span data-ttu-id="92ff1-111">Die Registrierung.</span><span class="sxs-lookup"><span data-stu-id="92ff1-111">The registry.</span></span> <span data-ttu-id="92ff1-112">Beachten Sie, dass eine Anwendung die untergeordneten Schlüssel Ihres eigenen Anwendungs Schlüssels verwenden sollte, um benutzerdefinierte Zeit Zonendaten zu speichern, anstatt die Unterschlüssel HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="92ff1-112">Note that an application should use the subkeys of its own application key to store custom time zone data rather than using the subkeys of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time Zones.</span></span>

- <span data-ttu-id="92ff1-113">Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="92ff1-113">Configuration files.</span></span>

- <span data-ttu-id="92ff1-114">Andere Systemdateien.</span><span class="sxs-lookup"><span data-stu-id="92ff1-114">Other system files.</span></span>

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a><span data-ttu-id="92ff1-115">So speichern Sie eine Zeitzone durch Serialisierung in eine RESX-Datei</span><span class="sxs-lookup"><span data-stu-id="92ff1-115">To save a time zone by serializing it to a .resx file</span></span>

1. <span data-ttu-id="92ff1-116">Rufen Sie eine vorhandene Zeitzone ab, oder erstellen Sie eine neue Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="92ff1-116">Retrieve an existing time zone or create a new time zone.</span></span>

   <span data-ttu-id="92ff1-117">Informationen zum Abrufen einer vorhandenen Zeitzone finden Sie unter Gewusst [wie: Zugreifen auf die vordefinierte UTC und lokale Zeit Zonen Objekte](access-utc-and-local.md) und Gewusst [wie: Instanziieren eines TimeZoneInfo-Objekts](instantiate-time-zone-info.md).</span><span class="sxs-lookup"><span data-stu-id="92ff1-117">To retrieve an existing time zone, see [How to: Access the predefined UTC and local time zone objects](access-utc-and-local.md) and [How to: Instantiate a TimeZoneInfo object](instantiate-time-zone-info.md).</span></span>

   <span data-ttu-id="92ff1-118">Um eine neue Zeitzone zu erstellen, rufen Sie eine der über Ladungen der- <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode auf.</span><span class="sxs-lookup"><span data-stu-id="92ff1-118">To create a new time zone, call one of the overloads of the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method.</span></span> <span data-ttu-id="92ff1-119">Weitere Informationen finden Sie unter Vorgehens [Weise: Erstellen von Zeitzonen ohne Anpassungsregeln](create-time-zones-without-adjustment-rules.md) und Gewusst [wie: Erstellen von Zeitzonen mit Anpassungsregeln](create-time-zones-with-adjustment-rules.md).</span><span class="sxs-lookup"><span data-stu-id="92ff1-119">For more information, see [How to: Create time zones without adjustment rules](create-time-zones-without-adjustment-rules.md) and [How to: Create time zones with adjustment rules](create-time-zones-with-adjustment-rules.md).</span></span>

2. <span data-ttu-id="92ff1-120">Rufen <xref:System.TimeZoneInfo.ToSerializedString%2A> Sie die-Methode auf, um eine Zeichenfolge zu erstellen, die die Daten der Zeitzone enthält.</span><span class="sxs-lookup"><span data-stu-id="92ff1-120">Call the <xref:System.TimeZoneInfo.ToSerializedString%2A> method to create a string that contains the time zone's data.</span></span>

3. <span data-ttu-id="92ff1-121">Instanziieren <xref:System.IO.StreamWriter> Sie ein-Objekt, indem Sie den Namen und optional den Pfad der RESX-Datei dem- <xref:System.IO.StreamWriter> Klassenkonstruktor bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="92ff1-121">Instantiate a <xref:System.IO.StreamWriter> object by providing the name and optionally the path of the .resx file to the <xref:System.IO.StreamWriter> class constructor.</span></span>

4. <span data-ttu-id="92ff1-122">Instanziieren Sie ein- <xref:System.Resources.ResXResourceWriter> Objekt, indem Sie das- <xref:System.IO.StreamWriter> Objekt an den- <xref:System.Resources.ResXResourceWriter> Klassenkonstruktor übergeben.</span><span class="sxs-lookup"><span data-stu-id="92ff1-122">Instantiate a <xref:System.Resources.ResXResourceWriter> object by passing the <xref:System.IO.StreamWriter> object to the <xref:System.Resources.ResXResourceWriter> class constructor.</span></span>

5. <span data-ttu-id="92ff1-123">Übergeben Sie die serialisierte Zeichenfolge der Zeitzone an die- <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="92ff1-123">Pass the time zone's serialized string to the <xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType> method.</span></span>

6. <span data-ttu-id="92ff1-124">Rufen Sie die <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="92ff1-124">Call the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method.</span></span>

7. <span data-ttu-id="92ff1-125">Rufen Sie die <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="92ff1-125">Call the <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> method.</span></span>

8. <span data-ttu-id="92ff1-126">Schließen Sie das <xref:System.IO.StreamWriter> Objekt, indem Sie seine-Methode aufrufen <xref:System.IO.StreamWriter.Close%2A> .</span><span class="sxs-lookup"><span data-stu-id="92ff1-126">Close the <xref:System.IO.StreamWriter> object by calling its <xref:System.IO.StreamWriter.Close%2A> method.</span></span>

9. <span data-ttu-id="92ff1-127">Fügen Sie die generierte RESX-Datei zum Visual Studio-Projekt der Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="92ff1-127">Add the generated .resx file to the application's Visual Studio project.</span></span>

10. <span data-ttu-id="92ff1-128">Stellen Sie mithilfe des Fensters **Eigenschaften** in Visual Studio sicher, dass die Eigenschaft Buildvorgang der Datei ". resx" auf **eingebettete Ressource** fest **gelegt ist.**</span><span class="sxs-lookup"><span data-stu-id="92ff1-128">Using the **Properties** window in Visual Studio, make sure that the .resx file's **Build Action** property is set to **Embedded Resource** .</span></span>

## <a name="example"></a><span data-ttu-id="92ff1-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92ff1-129">Example</span></span>

<span data-ttu-id="92ff1-130">Im folgenden Beispiel <xref:System.TimeZoneInfo> wird ein-Objekt, das die Central Standard Time darstellt, und ein-Objekt, das <xref:System.TimeZoneInfo> die Palmer Station darstellt, in der Antarktis-Zeit in eine .NET-XML-Ressourcen Datei mit dem Namen SerializedTimeZones. resx serialisiert.</span><span class="sxs-lookup"><span data-stu-id="92ff1-130">The following example serializes a <xref:System.TimeZoneInfo> object that represents Central Standard Time and a <xref:System.TimeZoneInfo> object that represents the Palmer Station, Antarctica time to a .NET XML resource file that is named SerializedTimeZones.resx.</span></span> <span data-ttu-id="92ff1-131">Central Standard Time wird normalerweise in der Registrierung definiert. Palmer Station, Antarktis ist eine benutzerdefinierte Zeitzone.</span><span class="sxs-lookup"><span data-stu-id="92ff1-131">Central Standard Time is typically defined in the registry; Palmer Station, Antarctica is a custom time zone.</span></span>

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

<span data-ttu-id="92ff1-132">In diesem Beispiel <xref:System.TimeZoneInfo> werden-Objekte so serialisiert, dass Sie zum Zeitpunkt der Kompilierung in einer Ressourcen Datei verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="92ff1-132">This example serializes <xref:System.TimeZoneInfo> objects so that they are available in a resource file at compile time.</span></span>

<span data-ttu-id="92ff1-133">Da die- <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> Methode einer .NET-XML-Ressourcen Datei umfassende Header Informationen hinzufügt, kann Sie nicht zum Hinzufügen von Ressourcen zu einer vorhandenen Datei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="92ff1-133">Because the <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> method adds complete header information to a .NET XML resource file, it cannot be used to add resources to an existing file.</span></span> <span data-ttu-id="92ff1-134">Im Beispiel wird dies behandelt, indem die Datei "SerializedTimeZones. resx" überprüft und, falls vorhanden, alle anderen Ressourcen als die beiden serialisierten Zeitzonen in einem generischen Objekt gespeichert werden <xref:System.Collections.Generic.Dictionary%602> .</span><span class="sxs-lookup"><span data-stu-id="92ff1-134">The example handles this by checking for the SerializedTimeZones.resx file and, if it exists, storing all of its resources other than the two serialized time zones to a generic <xref:System.Collections.Generic.Dictionary%602> object.</span></span> <span data-ttu-id="92ff1-135">Die vorhandene Datei wird dann gelöscht, und die vorhandenen Ressourcen werden der neuen Datei "SerializedTimeZones. resx" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="92ff1-135">The existing file is then deleted and the existing resources are added to a new SerializedTimeZones.resx file.</span></span> <span data-ttu-id="92ff1-136">Die serialisierten Zeit Zonendaten werden dieser Datei ebenfalls hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="92ff1-136">The serialized time zone data is also added to this file.</span></span>

<span data-ttu-id="92ff1-137">Die Schlüsselfelder (oder **Namen** ) der Ressourcen dürfen keine eingebetteten Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="92ff1-137">The key (or **Name** ) fields of resources should not contain embedded spaces.</span></span> <span data-ttu-id="92ff1-138">Die- <xref:System.String.Replace%28System.String%2CSystem.String%29> Methode wird aufgerufen, um alle eingebetteten Leerzeichen in den Zeit Zonen bezeichgern zu entfernen, bevor Sie der Ressourcen Datei zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="92ff1-138">The <xref:System.String.Replace%28System.String%2CSystem.String%29> method is called to remove all embedded spaces in the time zone identifiers before they are assigned to the resource file.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="92ff1-139">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="92ff1-139">Compiling the code</span></span>

<span data-ttu-id="92ff1-140">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="92ff1-140">This example requires:</span></span>

- <span data-ttu-id="92ff1-141">Ein Verweis auf System.Windows.Forms.dll und System.Core.dll dem Projekt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="92ff1-141">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="92ff1-142">Die folgenden Namespaces werden importiert:</span><span class="sxs-lookup"><span data-stu-id="92ff1-142">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="92ff1-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92ff1-143">See also</span></span>

- [<span data-ttu-id="92ff1-144">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="92ff1-144">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="92ff1-145">Übersicht über Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="92ff1-145">Time zone overview</span></span>](time-zone-overview.md)
- [<span data-ttu-id="92ff1-146">Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource</span><span class="sxs-lookup"><span data-stu-id="92ff1-146">How to: Restore time zones from an embedded resource</span></span>](restore-time-zones-from-an-embedded-resource.md)
