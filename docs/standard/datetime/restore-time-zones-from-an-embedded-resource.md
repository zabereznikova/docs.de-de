---
title: 'Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71fc4e04c87dfa3b83eabb06361d1da94a512a5e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656803"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="289d9-102">Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource</span><span class="sxs-lookup"><span data-stu-id="289d9-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="289d9-103">Dieses Thema beschreibt die Vorgehensweise beim Wiederherstellen von Zeitzonen, die in einer Ressourcendatei gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="289d9-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="289d9-104">Weitere Informationen und Anweisungen zum Speichern von Zeitzonen finden Sie unter [Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="289d9-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="289d9-105">Beim Deserialisieren eines TimeZoneInfo-Objekts aus einer eingebetteten Ressource</span><span class="sxs-lookup"><span data-stu-id="289d9-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="289d9-106">Wenn die Zeitzone abgerufen werden sollen, keine benutzerdefinierte Zeitzone ist, versuchen Sie es mit instanziiert die <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="289d9-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="289d9-107">Instanziieren einer <xref:System.Resources.ResourceManager> -Objekts durch Übergeben der vollqualifizierte Name der eingebetteten Ressourcendatei und einem Verweis auf die Assembly, die die Ressourcendatei enthält.</span><span class="sxs-lookup"><span data-stu-id="289d9-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="289d9-108">Wenn Sie den vollqualifizierten Namen der eingebetteten Ressourcendatei können nicht ermitteln, verwenden die [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) Manifest der Assembly zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="289d9-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="289d9-109">Ein `.mresource` Eintrag identifiziert die Ressource.</span><span class="sxs-lookup"><span data-stu-id="289d9-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="289d9-110">Im Beispiel des vollqualifizierten Ressourcennamens ist `SerializeTimeZoneData.SerializedTimeZones`.</span><span class="sxs-lookup"><span data-stu-id="289d9-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="289d9-111">Wenn die Ressourcendatei in der gleichen Assembly, die den Instanziierungscode Zeitzone enthält eingebettet ist, können Sie einen Verweis darauf abrufen, durch den Aufruf der `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="289d9-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="289d9-112">Wenn der Aufruf der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> -Methode fehlschlägt, oder ist eine benutzerdefinierte Zeitzone instanziiert werden, rufen Sie eine Zeichenfolge, die durch den Aufruf der serialisierten Zeitzone enthält die <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="289d9-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="289d9-113">Deserialisiert die Zeitzonendaten durch Aufrufen der <xref:System.TimeZoneInfo.FromSerializedString%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="289d9-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="289d9-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="289d9-114">Example</span></span>

<span data-ttu-id="289d9-115">Im folgenden Beispiel wird deserialisiert eine <xref:System.TimeZoneInfo> gespeichert, die in einer eingebetteten Ressourcendatei von .NET XML-Objekt.</span><span class="sxs-lookup"><span data-stu-id="289d9-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="289d9-116">Dieser Code veranschaulicht die Behandlung von Ausnahmen, um sicherzustellen, dass eine <xref:System.TimeZoneInfo> von der Anwendung benötigte Objekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="289d9-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="289d9-117">Zuerst wird versucht, instanziieren Sie ein <xref:System.TimeZoneInfo> Objekt durch Abrufen aus der Registrierung mithilfe der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="289d9-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="289d9-118">Wenn die Zeitzone nicht instanziiert werden kann, ruft Sie der Code aus der eingebetteten Ressourcendatei ab.</span><span class="sxs-lookup"><span data-stu-id="289d9-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="289d9-119">Da Daten für benutzerdefinierte Zeitzonen (Zeitzonen instanziiert werden mithilfe der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> Methode) werden nicht gespeichert in der Registrierung wird der Code nicht Aufrufen der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> instanziieren Sie die Zeitzone für Palmer, Antarktis.</span><span class="sxs-lookup"><span data-stu-id="289d9-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="289d9-120">Stattdessen es sofort überprüft, die eingebettete Ressourcendatei aus, um eine Zeichenfolge abzurufen, das die Zeitzone-Daten enthält, vor dem Aufrufen der <xref:System.TimeZoneInfo.FromSerializedString%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="289d9-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="289d9-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="289d9-121">Compiling the code</span></span>

<span data-ttu-id="289d9-122">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="289d9-122">This example requires:</span></span>

* <span data-ttu-id="289d9-123">Dass das Projekt ein Verweis auf "System.Windows.Forms.dll" und "System.Core.dll" hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="289d9-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="289d9-124">Dass die folgenden Namespaces importiert werden:</span><span class="sxs-lookup"><span data-stu-id="289d9-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="289d9-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="289d9-125">See also</span></span>

- [<span data-ttu-id="289d9-126">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="289d9-126">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="289d9-127">Übersicht über Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="289d9-127">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="289d9-128">Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource</span><span class="sxs-lookup"><span data-stu-id="289d9-128">How to: Save time zones to an embedded resource</span></span>](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
