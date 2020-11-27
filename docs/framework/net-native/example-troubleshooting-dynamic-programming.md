---
title: 'Beispiel: Problembehandlung bei dynamischer Programmierung'
ms.date: 03/30/2017
ms.assetid: 42ed860a-a022-4682-8b7f-7c9870784671
ms.openlocfilehash: 0cff232668b9eb65b09a22b14e4ae58673ccd6d0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288072"
---
# <a name="example-troubleshooting-dynamic-programming"></a><span data-ttu-id="3ef8e-102">Beispiel: Problembehandlung bei dynamischer Programmierung</span><span class="sxs-lookup"><span data-stu-id="3ef8e-102">Example: Troubleshooting Dynamic Programming</span></span>

> [!NOTE]
> <span data-ttu-id="3ef8e-103">Dieses Thema bezieht sich auf die .NET Native Developer Preview, ein Vorabrelease der Software.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-103">This topic refers to the .NET Native Developer Preview, which is pre-release software.</span></span> <span data-ttu-id="3ef8e-104">Sie können die Vorschau von der [Microsoft Connect-Website](https://go.microsoft.com/fwlink/?LinkId=394611) herunterladen (Registrierung erforderlich).</span><span class="sxs-lookup"><span data-stu-id="3ef8e-104">You can download the preview from the [Microsoft Connect website](https://go.microsoft.com/fwlink/?LinkId=394611) (requires registration).</span></span>  
  
 <span data-ttu-id="3ef8e-105">Nicht alle Metadaten-Suche-Fehler in apps, die mit der .net Native-Toolkette entwickelt wurden, führen zu einer Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-105">Not all metadata lookup failures in apps developed using the .NET Native tool chain result in an exception.</span></span>  <span data-ttu-id="3ef8e-106">Einige können sich auf unvorhersehbare Weise in einer App zeigen.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-106">Some can manifest in unpredictable ways in an app.</span></span>  <span data-ttu-id="3ef8e-107">Das folgende Beispiel zeigt eine Zugriffsverletzung, die durch das Verweisen auf ein Nullobjekt verursacht wurde:</span><span class="sxs-lookup"><span data-stu-id="3ef8e-107">The following example shows an access violation caused by referencing a null object:</span></span>  
  
```output
Access violation - code c0000005 (first chance)  
App!$3_App::Core::Util::NavigationArgs.Setup  
App!$3_App::Core::Util::NavigationArgs..ctor  
App!$0_App::Gibbon::Util::DesktopNavigationArgs..ctor  
App!$0_App::ViewModels::DesktopAppVM.NavigateToPage  
App!$3_App::Core::ViewModels::AppViewModel.NavigateToFirstPage  
App!$3_App::Core::ViewModels::AppViewModel::<HandleLaunch>d__a.MoveNext  
App!$43_System::Runtime::CompilerServices::AsyncMethodBuilderCore.CallMoveNext  
App!System::Action.InvokeClosedStaticThunk  
App!System::Action.Invoke  
App!$43_System::Threading::Tasks::AwaitTaskContinuation.InvokeAction  
App!$43_System::Threading::SendOrPostCallback.InvokeOpenStaticThunk  
[snip]  
```  
  
 <span data-ttu-id="3ef8e-108">Wir versuchen, diese Ausnahme mithilfe der dreistufigen Vorgehensweise zu behandeln, die im Abschnitt „Fehlende Metadaten manuell auflösen“ von [Erste Schritte](getting-started-with-net-native.md) erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-108">Let's try to troubleshoot this exception by using the three-step approach outlined in the "Manually resolve missing metadata" section of [Getting Started](getting-started-with-net-native.md).</span></span>  
  
## <a name="what-was-the-app-doing"></a><span data-ttu-id="3ef8e-109">Was hat die App getan?</span><span class="sxs-lookup"><span data-stu-id="3ef8e-109">What was the app doing?</span></span>  

 <span data-ttu-id="3ef8e-110">Zunächst muss die `async`-Schlüsselwortmaschinerie an der Basis des Stapels beachtet werden.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-110">The first thing to note is the `async` keyword machinery at the base of the stack.</span></span>  <span data-ttu-id="3ef8e-111">Zu bestimmen, welche Aktion die App in einer `async`-Methode wirklich ausgeführt hat, kann problematisch sein, da der Stapel den Kontext des ursprünglichen Aufrufs verloren und den `async`-Code in einem anderen Thread ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-111">Determining what the app was really doing in an `async` method can be problematic, because the stack has lost the context of the originating call and has run the `async` code on a different thread.</span></span> <span data-ttu-id="3ef8e-112">Allerdings können wir ableiten, dass die App versucht, die erste Seite zu laden.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-112">However, we can deduce that the app is trying to load its first page.</span></span>  <span data-ttu-id="3ef8e-113">In der Implementierung für `NavigationArgs.Setup` hat der folgende Code die Zugriffsverletzung verursacht:</span><span class="sxs-lookup"><span data-stu-id="3ef8e-113">In the implementation for `NavigationArgs.Setup`, the following code caused the access violation:</span></span>  
  
`AppViewModel.Current.LayoutVM.PageMap`  
  
 <span data-ttu-id="3ef8e-114">In diesem Fall war die `LayoutVM`-Eigenschaft für `AppViewModel.Current`**NULL**.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-114">In this instance, the `LayoutVM` property on `AppViewModel.Current` was **null**.</span></span>  <span data-ttu-id="3ef8e-115">Das Fehlen einiger Metadaten hat ein leicht unterschiedliches Verhalten verursacht und dazu geführt, dass eine Eigenschaft anstatt eines Sets nicht initialisiert wurde, wie die App erwartet hat.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-115">Some absence of metadata caused a subtle behavior difference and resulted in a property being uninitialized instead of set, as the app expected.</span></span>  <span data-ttu-id="3ef8e-116">Zum Verstehen der Situation könnte es helfen, einen Haltepunkt im Code an der Stelle festzulegen, an der `LayoutVM` initialisiert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-116">Setting a breakpoint in the code where `LayoutVM` should have been initialized might throw light on the situation.</span></span>  <span data-ttu-id="3ef8e-117">Beachten Sie jedoch, dass der Typ von `LayoutVM``App.Core.ViewModels.Layout.LayoutApplicationVM` lautet.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-117">However, note that `LayoutVM`’s type is `App.Core.ViewModels.Layout.LayoutApplicationVM`.</span></span>  <span data-ttu-id="3ef8e-118">Die einzige bisher in der Datei "rd.xml" vorhandene Metadatenrichtlinnie ist:</span><span class="sxs-lookup"><span data-stu-id="3ef8e-118">The only metadata directive present so far in the rd.xml file is:</span></span>  
  
```xml  
<Namespace Name="App.ViewModels" Browse="Required Public" Dynamic="Required Public" />  
```  
  
 <span data-ttu-id="3ef8e-119">Eine wahrscheinlicher Ursache für den Fehler besteht darin, dass `App.Core.ViewModels.Layout.LayoutApplicationVM` Metadaten fehlen, da es sich in einem anderen Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-119">A likely candidate for the failure is that `App.Core.ViewModels.Layout.LayoutApplicationVM` is missing metadata because it's in a different namespace.</span></span>  
  
 <span data-ttu-id="3ef8e-120">In diesem Fall wurde das Problem durch Hinzufügen einer Laufzeitanweisung für `App.Core.ViewModels` behoben.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-120">In this case, adding a runtime directive for `App.Core.ViewModels` resolved the issue.</span></span> <span data-ttu-id="3ef8e-121">Die Grundursache war ein API-Aufruf an die <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType>-Methode, die **NULL** zurückgegeben hat. Die App hat das Problem ignoriert, bis ein Absturz aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-121">The root cause was an API call to the <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType> method that returned **null**, and the app silently ignored the problem until a crash occurred.</span></span>  
  
 <span data-ttu-id="3ef8e-122">Bei der dynamischen Programmierung empfiehlt es sich, bei der Verwendung von Reflection-APIs unter .net Native die <xref:System.Type.GetType%2A?displayProperty=nameWithType> über Ladungen zu verwenden, die bei einem Fehler eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-122">In dynamic programming, a good practice when using reflection APIs under .NET Native is to use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> overloads that throw an exception on failure.</span></span>  
  
## <a name="is-this-an-isolated-case"></a><span data-ttu-id="3ef8e-123">Handelt es sich um einen Einzelfall?</span><span class="sxs-lookup"><span data-stu-id="3ef8e-123">Is this an isolated case?</span></span>  

 <span data-ttu-id="3ef8e-124">Andere Probleme können mit `App.Core.ViewModels` ebenfalls auftreten.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-124">Other issues might also arise when using `App.Core.ViewModels`.</span></span>  <span data-ttu-id="3ef8e-125">Sie müssen entscheiden, ob es sich lohnt, jede Ausnahme aufgrund von fehlenden Metadaten zu identifizieren und zu lösen, oder ob Sie Zeit sparen und Anweisungen für eine größere Typenklasse hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-125">You must decide whether it’s worth identifying and fixing each missing metadata exception, or saving time and adding directives for a larger class of types.</span></span>  <span data-ttu-id="3ef8e-126">Hier ist das Hinzufügen von `dynamic`-Metadaten für `App.Core.ViewModels` möglicherweise der beste Ansatz, wenn die daraus resultierende Größenzunahme der Ausgabebinärdatei kein Problem ist.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-126">Here, adding `dynamic` metadata for `App.Core.ViewModels` might be the best approach if the resulting size increase of the output binary isn’t an issue.</span></span>  
  
## <a name="could-the-code-be-rewritten"></a><span data-ttu-id="3ef8e-127">Könnte der Code neu geschrieben werden?</span><span class="sxs-lookup"><span data-stu-id="3ef8e-127">Could the code be rewritten?</span></span>  

 <span data-ttu-id="3ef8e-128">Hätte die App `typeof(LayoutApplicationVM)` anstelle von `Type.GetType("LayoutApplicationVM")` verwendet, hätte die Toolkette `browse`-Metadaten beibehalten können.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-128">If the app had used `typeof(LayoutApplicationVM)` instead of `Type.GetType("LayoutApplicationVM")`, the tool chain could have preserved `browse` metadata.</span></span>  <span data-ttu-id="3ef8e-129">Jedoch wären immer noch keine `invoke`-Metadaten erstellt worden, was zu einer [MissingMetadataException](missingmetadataexception-class-net-native.md)-Ausnahme beim Instanziieren des Typs geführt hätte.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-129">However, it still wouldn't have created `invoke` metadata, which would have led to a [MissingMetadataException](missingmetadataexception-class-net-native.md) exception when instantiating the type.</span></span> <span data-ttu-id="3ef8e-130">Um die Ausnahme zu verhindern, müssten Sie eine Laufzeitanweisung für den Namespace oder den Typ hinzufügen, der die `dynamic`-Richtlinie angibt.</span><span class="sxs-lookup"><span data-stu-id="3ef8e-130">To prevent the exception, you'd still have to add a runtime directive for the namespace or the type that specifies the `dynamic` policy.</span></span> <span data-ttu-id="3ef8e-131">Informationen zu Laufzeitanweisungen finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei der Laufzeitanweisungen (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="3ef8e-131">For information on runtime directives, see the [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ef8e-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ef8e-132">See also</span></span>

- [<span data-ttu-id="3ef8e-133">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="3ef8e-133">Getting Started</span></span>](getting-started-with-net-native.md)
- [<span data-ttu-id="3ef8e-134">Beispiel: Behandeln von Ausnahmen beim Binden von Daten</span><span class="sxs-lookup"><span data-stu-id="3ef8e-134">Example: Handling Exceptions When Binding Data</span></span>](example-handling-exceptions-when-binding-data.md)
