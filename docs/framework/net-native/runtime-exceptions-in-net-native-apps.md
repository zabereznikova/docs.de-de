---
title: Laufzeitausnahmen in .NET Native-Apps
ms.date: 03/30/2017
ms.assetid: 5f050181-8fdd-4a4e-9d16-f84c22a88a97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06e07c41d398c0792094b4481a38c69b2ba73004
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208279"
---
# <a name="runtime-exceptions-in-net-native-apps"></a><span data-ttu-id="c7df8-102">Laufzeitausnahmen in .NET Native-Apps</span><span class="sxs-lookup"><span data-stu-id="c7df8-102">Runtime Exceptions in .NET Native Apps</span></span>
<span data-ttu-id="c7df8-103">Es ist wichtig, die Releasebuilds Ihrer App für die universelle Windows-Plattform auf den Zielplattformen zu testen, da die Debug- und Releasekonfigurationen völlig unterschiedlich sind.</span><span class="sxs-lookup"><span data-stu-id="c7df8-103">It is important to test the release builds of your Universal Windows Platform app on their target platforms because the debug and release configurations are completely different.</span></span> <span data-ttu-id="c7df8-104">Die Debugkonfiguration verwendet standardmäßig die .NET Core-Laufzeit zum Kompilieren der App, während die Releasekonfiguration .NET Native verwendet, um die App in systemeigenen Code zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="c7df8-104">By default, the debug configuration uses the .NET Core runtime to compile your app, but the release configuration uses .NET Native to compile your app to native code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c7df8-105">Informationen zum Umgang mit den [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), und [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) Ausnahmen, die Sie möglicherweise Beim Testen der Releaseversionen Ihrer App auftreten, finden Sie unter "Schritt 4: Manuelles Beheben fehlender Metadaten: in der [Einstieg](../../../docs/framework/net-native/getting-started-with-net-native.md) Thema sowie [Reflektion und .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md) und [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="c7df8-105">For information on dealing with the [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md), and [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) exceptions that you may encounter when testing the release versions of your app, see  "Step 4: Manually resolve missing metadata: in the [Getting Started](../../../docs/framework/net-native/getting-started-with-net-native.md) topic, as well as [Reflection and .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md) and [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
## <a name="debug-and-release-builds"></a><span data-ttu-id="c7df8-106">Debugbuilds und Releasebuilds</span><span class="sxs-lookup"><span data-stu-id="c7df8-106">Debug and release builds</span></span>  
 <span data-ttu-id="c7df8-107">Wenn der Debugbuild unter Verwendung der .NET Core-Laufzeit ausgeführt wird, wurde er nicht in systemeigenen Code kompiliert.</span><span class="sxs-lookup"><span data-stu-id="c7df8-107">When the debug build executes against the .NET Core runtime, it has not been compiled to native code.</span></span> <span data-ttu-id="c7df8-108">Dadurch werden alle Dienste, die normalerweise von der Laufzeit bereitgestellt werden, für Ihre App verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7df8-108">This makes all of the services ordinarily provided by the runtime available to your app.</span></span>  
  
 <span data-ttu-id="c7df8-109">Andererseits werden der Releasebuild für die Zielplattformen in systemeigenen Code kompiliert, die meisten Abhängigkeiten von externen Laufzeiten und Bibliotheken entfernt und Code für maximale Leistung optimiert.</span><span class="sxs-lookup"><span data-stu-id="c7df8-109">On the other hand, the release build compiles to native code for its target platforms, removes most dependencies on external runtimes and libraries, and heavily optimizes code for maximum performance.</span></span>  
  
 <span data-ttu-id="c7df8-110">Beim Debuggen von Releasebuilds, die mithilfe von .NET Native kompiliert wurden, geschieht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c7df8-110">When you debug release builds that are compiled by using .NET Native:</span></span>  
  
-   <span data-ttu-id="c7df8-111">Sie verwenden die .NET Native-Debug-Engine, die sich von den normalen .NET-Debugtools unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="c7df8-111">You use the .NET Native debug engine, which is different from the normal .NET debugging tools.</span></span>  
  
-   <span data-ttu-id="c7df8-112">Die Größe Ihrer ausführbaren Datei wird so weit wie möglich reduziert.</span><span class="sxs-lookup"><span data-stu-id="c7df8-112">The size of your executable is reduced as much as possible.</span></span> <span data-ttu-id="c7df8-113">Eine der Methoden, durch die .NET Native die Größe einer ausführbaren Datei verringert, besteht darin, dass Laufzeitausnahmemeldungen erheblich gekürzt werden. Dieses Thema wird ausführlicher im Abschnitt [Runtime exception messages](#Messages) erörtert.</span><span class="sxs-lookup"><span data-stu-id="c7df8-113">One of the ways that .NET Native reduces the size of an executable is by significantly trimming runtime exception messages, a topic discussed in greater detail in the [Runtime exception messages](#Messages) section.</span></span>  
  
-   <span data-ttu-id="c7df8-114">Der Code wird stark optimiert.</span><span class="sxs-lookup"><span data-stu-id="c7df8-114">Your code is heavily optimized.</span></span> <span data-ttu-id="c7df8-115">Dies bedeutet, dass nach Möglichkeit Inlining verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7df8-115">This means that inlining is used whenever possible.</span></span> <span data-ttu-id="c7df8-116">(Beim Inlining wird Code aus externen Routinen in die aufrufende Routine verschoben.)   Die Tatsache, dass .NET Native eine spezielle Laufzeit bietet und aggressives Inlining implementiert, wirkt sich auf die beim Debuggen angezeigte Aufrufliste aus.</span><span class="sxs-lookup"><span data-stu-id="c7df8-116">(Inlining moves code from external routines into the calling routine.)   The fact that .NET Native provides a specialized runtime and implements aggressive inlining  affects the call stack that is displayed when debugging.</span></span>  <span data-ttu-id="c7df8-117">Weitere Informationen finden Sie im Abschnitt [Runtime call stack](#CallStack) .</span><span class="sxs-lookup"><span data-stu-id="c7df8-117">For more information, see the [Runtime call stack](#CallStack) section.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7df8-118">Sie können steuern, ob die Debug- und Releasebuilds mit der .NET Native-Toolkette kompiliert werden, indem Sie das Kontrollkästchen **Mit .NET Native-Toolkette kompilieren** aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c7df8-118">You can control whether the debug and release builds are compiled with the .NET Native tool chain by checking or unchecking the **Compile with .NET Native tool chain** box.</span></span>   <span data-ttu-id="c7df8-119">Beachten Sie jedoch, dass die Produktionsversion Ihrer App vom Windows Store immer mit der .NET Native-Toolkette kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="c7df8-119">Note, however, that the Windows Store will always compile the production version of your app with the .NET Native tool chain.</span></span>  
  
<a name="Messages"></a>   
## <a name="runtime-exception-messages"></a><span data-ttu-id="c7df8-120">Runtime exception messages</span><span class="sxs-lookup"><span data-stu-id="c7df8-120">Runtime exception messages</span></span>  
 <span data-ttu-id="c7df8-121">Um die Größe ausführbarer Anwendungsdateien zu minimieren, schließt .NET Native nicht den vollständigen Text von Ausnahmemeldungen ein.</span><span class="sxs-lookup"><span data-stu-id="c7df8-121">To minimize application executable size, .NET Native does not include the full text of exception messages.</span></span> <span data-ttu-id="c7df8-122">Daher wird bei Laufzeitausnahmen, die in Releasebuilds ausgelöst werden, u. U. nicht der vollständige Text der Ausnahmemeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7df8-122">As a result, runtime exceptions thrown in release builds may not display the full text of exception messages.</span></span> <span data-ttu-id="c7df8-123">Stattdessen kann der Text eine Teilzeichenfolge und einen Link umfassen, über den weitere Informationen abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="c7df8-123">Instead, the text may consist of a substring along with a link to follow for more information.</span></span> <span data-ttu-id="c7df8-124">Beispielsweise können Ausnahmeinformationen wie folgt angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="c7df8-124">For example, the exception information may appear as:</span></span>  
  
```  
Exception thrown: '$16_System.AggregateException' in Unknown Module.  
  
Additional information: AggregateException_ctor_DefaultMessage  
  
If there is a handler for this exception, the program may be safely continued.  
```  
  
 <span data-ttu-id="c7df8-125">Wenn Sie die vollständige Ausnahmemeldung benötigen, führen Sie stattdessen den Debugbuild aus.</span><span class="sxs-lookup"><span data-stu-id="c7df8-125">If you need the complete exception message,  run the debug build instead.</span></span> <span data-ttu-id="c7df8-126">Beispielsweise könnte die vorherigen Ausnahmeinformationen aus dem Releasebuild im Debugbuild wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="c7df8-126">For example, the previous exception information  from the release build might appear as follows in the debug build:</span></span>  
  
```  
Exception thrown: 'System.AggregateException' in NativeApp.exe.  
  
Additional information: Value does not fall within the expected range.  
```  
  
<a name="CallStack"></a>   
## <a name="runtime-call-stack"></a><span data-ttu-id="c7df8-127">Runtime call stack</span><span class="sxs-lookup"><span data-stu-id="c7df8-127">Runtime call stack</span></span>  
 <span data-ttu-id="c7df8-128">Durch das Inlining und andere Optimierungen kann es schwierig sein, den Pfad zu einer Laufzeitausnahme anhand der Aufrufliste, die von einer App angezeigt wird, die von der .NET Native-Toolkette kompiliert wurde, eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c7df8-128">Because of inlining and other optimizations, the call stack displayed by an app compiled by the .NET Native tool chain may not help you to  clearly identify the path to a runtime exception.</span></span>  
  
 <span data-ttu-id="c7df8-129">Um die vollständige Aufrufliste zu erhalten, führen Sie stattdessen den Debugbuild aus.</span><span class="sxs-lookup"><span data-stu-id="c7df8-129">To get the full stack, run the debug build instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7df8-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7df8-130">See also</span></span>

- [<span data-ttu-id="c7df8-131">Debuggen universeller Windows-Apps, die in .NET Native kompiliert wurden</span><span class="sxs-lookup"><span data-stu-id="c7df8-131">Debugging .NET Native Windows Universal Apps</span></span>](https://devblogs.microsoft.com/devops/debugging-net-native-windows-universal-apps/)
- [<span data-ttu-id="c7df8-132">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="c7df8-132">Getting Started</span></span>](../../../docs/framework/net-native/getting-started-with-net-native.md)
