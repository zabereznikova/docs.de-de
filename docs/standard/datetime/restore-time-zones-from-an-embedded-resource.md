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
ms.openlocfilehash: 98813bf6685be78d33ebd5cc5e8c07a61a811c25
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106753"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a><span data-ttu-id="ae2bd-102">Vorgehensweise: Wiederherstellen von Zeitzonen aus einer eingebetteten Ressource</span><span class="sxs-lookup"><span data-stu-id="ae2bd-102">How to: Restore time zones from an embedded resource</span></span>

<span data-ttu-id="ae2bd-103">In diesem Thema wird beschrieben, wie Zeitzonen wieder hergestellt werden, die in einer Ressourcen Datei gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-103">This topic describes how to restore time zones that have been saved in a resource file.</span></span> <span data-ttu-id="ae2bd-104">Weitere Informationen und Anweisungen zum Speichern von Zeitzonen finden [Sie unter Gewusst wie: Speichert Zeitzonen in einer eingebetteten Ressource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span><span class="sxs-lookup"><span data-stu-id="ae2bd-104">For information and instructions about saving time zones, see [How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md).</span></span>

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a><span data-ttu-id="ae2bd-105">So deserialisieren Sie ein TimeZoneInfo-Objekt aus einer eingebetteten Ressource</span><span class="sxs-lookup"><span data-stu-id="ae2bd-105">To deserialize a TimeZoneInfo object from an embedded resource</span></span>

1. <span data-ttu-id="ae2bd-106">Wenn die abzurufende Zeitzone keine benutzerdefinierte Zeitzone ist, versuchen Sie, Sie mithilfe der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> -Methode zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-106">If the time zone to be retrieved is not a custom time zone, try to instantiate it by using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span>

2. <span data-ttu-id="ae2bd-107">Instanziieren Sie <xref:System.Resources.ResourceManager> ein-Objekt, indem Sie den voll qualifizierten Namen der eingebetteten Ressourcen Datei und einen Verweis auf die Assembly, die die Ressourcen Datei enthält, übergeben.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-107">Instantiate a <xref:System.Resources.ResourceManager> object by passing the fully qualified name of the embedded resource file and a reference to the assembly that contains the resource file.</span></span>

   <span data-ttu-id="ae2bd-108">Wenn Sie den voll qualifizierten Namen der eingebetteten Ressourcen Datei nicht ermitteln können, verwenden Sie den [Ildasm. exe (IL-Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) , um das Assemblymanifest zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-108">If you cannot determine the fully qualified name of the embedded resource file, use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's manifest.</span></span> <span data-ttu-id="ae2bd-109">Ein `.mresource` Eintrag identifiziert die Ressource.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-109">An `.mresource` entry identifies the resource.</span></span> <span data-ttu-id="ae2bd-110">Im Beispiel lautet `SerializeTimeZoneData.SerializedTimeZones`der voll qualifizierte Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-110">In the example, the resource's fully qualified name is `SerializeTimeZoneData.SerializedTimeZones`.</span></span>

   <span data-ttu-id="ae2bd-111">Wenn die Ressourcen Datei in dieselbe Assembly eingebettet ist, in der der Zeit Zonen-instanzierationscode enthalten ist, können Sie einen Verweis darauf abrufen `static` ,`Shared` indem Sie die <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> -Methode (in Visual Basic) aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-111">If the resource file is embedded in the same assembly that contains the time zone instantiation code, you can retrieve a reference to it by calling the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> method.</span></span>

3. <span data-ttu-id="ae2bd-112">Wenn der Aufruf <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> der-Methode fehlschlägt oder eine benutzerdefinierte Zeitzone instanziiert werden soll, rufen Sie eine Zeichenfolge ab, die die serialisierte Zeitzone enthält, indem <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> Sie die-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-112">If the call to the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method fails, or if a custom time zone is to be instantiated, retrieve a string that contains the serialized time zone by calling the <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> method.</span></span>

4. <span data-ttu-id="ae2bd-113">Deserialisieren Sie die Zeit Zonendaten, indem <xref:System.TimeZoneInfo.FromSerializedString%2A> Sie die-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-113">Deserialize the time zone data by calling the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="example"></a><span data-ttu-id="ae2bd-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ae2bd-114">Example</span></span>

<span data-ttu-id="ae2bd-115">Im folgenden Beispiel wird ein <xref:System.TimeZoneInfo> -Objekt deserialisiert, das in einer eingebetteten .NET-XML-Ressourcen Datei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-115">The following example deserializes a <xref:System.TimeZoneInfo> object stored in an embedded .NET XML resource file.</span></span>

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

<span data-ttu-id="ae2bd-116">Dieser Code veranschaulicht die Ausnahmebehandlung, um sicher <xref:System.TimeZoneInfo> zustellen, dass ein für die Anwendung erforderliches-Objekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-116">This code illustrates exception handling to ensure that a <xref:System.TimeZoneInfo> object required by the application is present.</span></span> <span data-ttu-id="ae2bd-117">Zuerst wird versucht, ein <xref:System.TimeZoneInfo> -Objekt zu instanziieren, indem es mithilfe der <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> -Methode aus der Registrierung abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-117">It first tries to instantiate a <xref:System.TimeZoneInfo> object by retrieving it from the registry using the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> method.</span></span> <span data-ttu-id="ae2bd-118">Wenn die Zeitzone nicht instanziiert werden kann, ruft der Code Sie aus der eingebetteten Ressourcen Datei ab.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-118">If the time zone cannot be instantiated, the code retrieves it from the embedded resource file.</span></span>

<span data-ttu-id="ae2bd-119">Da Daten für benutzerdefinierte Zeitzonen (mit der <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> -Methode instanziierte Zeitzonen) nicht in der Registrierung gespeichert werden, <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> ruft der Code nicht auf, um die Zeitzone für Palmer, Antarktis zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-119">Because data for custom time zones (time zones instantiated by using the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method) are not stored in the registry, the code does not call the <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> to instantiate the time zone for Palmer, Antarctica.</span></span> <span data-ttu-id="ae2bd-120">Stattdessen sucht es sofort nach der eingebetteten Ressourcen Datei, um eine Zeichenfolge abzurufen, die die Daten der Zeitzone enthält, bevor die <xref:System.TimeZoneInfo.FromSerializedString%2A> -Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-120">Instead, it immediately looks to the embedded resource file to retrieve a string that contains the time zone's data before it calls the <xref:System.TimeZoneInfo.FromSerializedString%2A> method.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="ae2bd-121">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="ae2bd-121">Compiling the code</span></span>

<span data-ttu-id="ae2bd-122">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ae2bd-122">This example requires:</span></span>

- <span data-ttu-id="ae2bd-123">Dem Projekt wird ein Verweis auf "System. Windows. Forms. dll" und "System. Core. dll" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ae2bd-123">That a reference to System.Windows.Forms.dll and System.Core.dll be added to the project.</span></span>

- <span data-ttu-id="ae2bd-124">Die folgenden Namespaces werden importiert:</span><span class="sxs-lookup"><span data-stu-id="ae2bd-124">That the following namespaces be imported:</span></span>

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a><span data-ttu-id="ae2bd-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae2bd-125">See also</span></span>

- [<span data-ttu-id="ae2bd-126">Datumsangaben, Uhrzeiten und Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="ae2bd-126">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="ae2bd-127">Übersicht über Zeitzonen</span><span class="sxs-lookup"><span data-stu-id="ae2bd-127">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="ae2bd-128">Vorgehensweise: Speichern von Zeitzonen in einer eingebetteten Ressource</span><span class="sxs-lookup"><span data-stu-id="ae2bd-128">How to: Save time zones to an embedded resource</span></span>](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
