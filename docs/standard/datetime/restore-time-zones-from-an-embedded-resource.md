---
title: 'Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], deserializing
- time zones [.NET], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
ms.openlocfilehash: 1dd3dff2441ac5e21f3ebf97d58919a7c65d42c5
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063429"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="402dc-102">Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource</span><span class="sxs-lookup"><span data-stu-id="402dc-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="402dc-103">In diesem Thema wird beschrieben, wie Zeitzonen wieder hergestellt werden, die in einer Ressourcen Datei gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="402dc-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="402dc-104">Weitere Informationen und Anweisungen zum Speichern von Zeitzonen finden Sie unter Gewusst [wie: Speichern von Zeitzonen in einer eingebetteten Ressource](save-time-zones-to-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="402dc-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="402dc-105">So deserialisieren Sie ein TimeZoneInfo-Objekt aus einer eingebetteten Ressource</span><span class="sxs-lookup"><span data-stu-id="402dc-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="402dc-106">Wenn die abzurufende Zeitzone keine benutzerdefinierte Zeitzone ist, versuchen Sie, Sie mithilfe der-Methode zu instanziieren <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> .</span><span class="sxs-lookup"><span data-stu-id="402dc-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="402dc-107">Instanziieren <xref:System.Resources.ResourceManager> Sie ein-Objekt, indem Sie den voll qualifizierten Namen der eingebetteten Ressourcen Datei und einen Verweis auf die Assembly, die die Ressourcen Datei enthält, übergeben.</span><span class="sxs-lookup"><span data-stu-id="402dc-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="402dc-108">Wenn Sie den voll qualifizierten Namen der eingebetteten Ressourcen Datei nicht ermitteln können, verwenden Sie den [Ildasm.exe (IL-Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) , um das Assemblymanifest zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="402dc-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="402dc-109">Ein `.mresource` Eintrag identifiziert die Ressource.</span><span class="sxs-lookup"><span data-stu-id="402dc-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="402dc-110">Im Beispiel lautet der voll qualifizierte Name der Ressource `SerializeTimeZoneData.SerializedTimeZones` .</span><span class="sxs-lookup"><span data-stu-id="402dc-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="402dc-111">Wenn die Ressourcen Datei in dieselbe Assembly eingebettet ist, in der der Zeit Zonen-instanzierationscode enthalten ist, können Sie einen Verweis darauf abrufen, indem Sie die- `static` `Shared` Methode (in Visual Basic) aufrufen <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> .</span><span class="sxs-lookup"><span data-stu-id="402dc-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="402dc-112">Wenn der Aufruf der- <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> Methode fehlschlägt oder eine benutzerdefinierte Zeitzone instanziiert werden soll, rufen Sie eine Zeichenfolge ab, die die serialisierte Zeitzone enthält, indem Sie die- <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="402dc-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="402dc-113">Deserialisieren Sie die Zeit Zonendaten, indem Sie die- <xref:System.TimeZoneInfo.FromSerializedString%2A> Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="402dc-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="402dc-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="402dc-114">Example</span></span>

<span data-ttu-id="402dc-115">Im folgenden Beispiel wird ein-Objekt deserialisiert, das <xref:System.TimeZoneInfo> in einer eingebetteten .NET-XML-Ressourcen Datei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="402dc-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="402dc-116">Dieser Code veranschaulicht die Ausnahmebehandlung, um sicherzustellen, dass ein <xref:System.TimeZoneInfo> für die Anwendung erforderliches-Objekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="402dc-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="402dc-117">Zuerst wird versucht, ein-Objekt zu instanziieren, <xref:System.TimeZoneInfo> indem es mithilfe der-Methode aus der Registrierung abgerufen wird <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> .</span><span class="sxs-lookup"><span data-stu-id="402dc-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="402dc-118">Wenn die Zeitzone nicht instanziiert werden kann, ruft der Code Sie aus der eingebetteten Ressourcen Datei ab.</span><span class="sxs-lookup"><span data-stu-id="402dc-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="402dc-119">Da Daten für benutzerdefinierte Zeitzonen (mit der-Methode instanziierte Zeitzonen <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> ) nicht in der Registrierung gespeichert werden, ruft der Code nicht <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> auf, um die Zeitzone für Palmer, Antarktis zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="402dc-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="402dc-120">Stattdessen sucht es sofort nach der eingebetteten Ressourcen Datei, um eine Zeichenfolge abzurufen, die die Daten der Zeitzone enthält, bevor die-Methode aufgerufen wird <xref:System.TimeZoneInfo.FromSerializedString%2A> .</span><span class="sxs-lookup"><span data-stu-id="402dc-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="402dc-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="402dc-121">Compiling the code</span></span>

<span data-ttu-id="402dc-122">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="402dc-122">This example requires:</span></span>

- <span data-ttu-id="402dc-123">Ein Verweis auf System.Windows.Forms.dll und System.Core.dll dem Projekt hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="402dc-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="402dc-124">Die folgenden Namespaces werden importiert:</span><span class="sxs-lookup"><span data-stu-id="402dc-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="402dc-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="402dc-125">See also</span></span>

- [<span data-ttu-id="402dc-126">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="402dc-126">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="402dc-127">Übersicht über Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="402dc-127">Time zone overview</span></span>](time-zone-overview.md)
- [<span data-ttu-id="402dc-128">Gewusst wie: Speichern von Zeitzonen in einer eingebetteten Ressource</span><span class="sxs-lookup"><span data-stu-id="402dc-128">How to: Save time zones to an embedded resource</span></span>](save-time-zones-to-an-embedded-resource.md)
