---
title: 'Beispiel: Problembehandlung bei dynamischer Programmierung'
ms.date: 03/30/2017
ms.assetid: 42ed860a-a022-4682-8b7f-7c9870784671
ms.openlocfilehash: ff179854066d024a89cb5a84a19d0b9bb054d6e5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128438"
---
# <a name="example-troubleshooting-dynamic-programming"></a>Beispiel: Problembehandlung bei dynamischer Programmierung
> [!NOTE]
> Dieses Thema bezieht sich auf die .NET Native Developer Preview, ein Vorabrelease der Software. Sie können die Vorschau von der [Microsoft Connect-Website](https://go.microsoft.com/fwlink/?LinkId=394611) herunterladen (Registrierung erforderlich).  
  
 Nicht alle Metadaten-Suche-Fehler in apps, die mit der .net Native-Toolkette entwickelt wurden, führen zu einer Ausnahme.  Einige können sich auf unvorhersehbare Weise in einer App zeigen.  Das folgende Beispiel zeigt eine Zugriffsverletzung, die durch das Verweisen auf ein Nullobjekt verursacht wurde:  
  
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
  
 Wir versuchen, diese Ausnahme mithilfe der dreistufigen Vorgehensweise zu behandeln, die im Abschnitt „Fehlende Metadaten manuell auflösen“ von [Erste Schritte](getting-started-with-net-native.md) erläutert wird.  
  
## <a name="what-was-the-app-doing"></a>Was hat die App gerade getan?  
 Zunächst muss die `async`-Schlüsselwortmaschinerie an der Basis des Stapels beachtet werden.  Zu bestimmen, welche Aktion die App in einer `async`-Methode wirklich ausgeführt hat, kann problematisch sein, da der Stapel den Kontext des ursprünglichen Aufrufs verloren und den `async`-Code in einem anderen Thread ausgeführt hat. Allerdings können wir ableiten, dass die App versucht, die erste Seite zu laden.  In der Implementierung für `NavigationArgs.Setup` hat der folgende Code die Zugriffsverletzung verursacht:  
  
`AppViewModel.Current.LayoutVM.PageMap`  
  
 In diesem Fall war die `LayoutVM`-Eigenschaft für `AppViewModel.Current`**NULL**.  Das Fehlen einiger Metadaten hat ein leicht unterschiedliches Verhalten verursacht und dazu geführt, dass eine Eigenschaft anstatt eines Sets nicht initialisiert wurde, wie die App erwartet hat.  Zum Verstehen der Situation könnte es helfen, einen Haltepunkt im Code an der Stelle festzulegen, an der `LayoutVM` initialisiert werden sollte.  Beachten Sie jedoch, dass der Typ von `LayoutVM``App.Core.ViewModels.Layout.LayoutApplicationVM` lautet.  Die einzige bisher in der Datei "rd.xml" vorhandene Metadatenrichtlinnie ist:  
  
```xml  
<Namespace Name="App.ViewModels" Browse="Required Public" Dynamic="Required Public" />  
```  
  
 Eine wahrscheinlicher Ursache für den Fehler besteht darin, dass `App.Core.ViewModels.Layout.LayoutApplicationVM` Metadaten fehlen, da es sich in einem anderen Namespace befindet.  
  
 In diesem Fall wurde das Problem durch Hinzufügen einer Laufzeitanweisung für `App.Core.ViewModels` behoben. Die Grundursache war ein API-Aufruf an die <xref:System.Type.GetType%28System.String%29?displayProperty=nameWithType>-Methode, die **NULL** zurückgegeben hat. Die App hat das Problem ignoriert, bis ein Absturz aufgetreten ist.  
  
 Bei der dynamischen Programmierung empfiehlt es sich, bei der Verwendung von Reflection-APIs unter .net Native die <xref:System.Type.GetType%2A?displayProperty=nameWithType> über Ladungen zu verwenden, die bei einem Fehler eine Ausnahme auslösen.  
  
## <a name="is-this-an-isolated-case"></a>Handelt es sich um einen Einzelfall?  
 Andere Probleme können mit `App.Core.ViewModels` ebenfalls auftreten.  Sie müssen entscheiden, ob es sich lohnt, jede Ausnahme aufgrund von fehlenden Metadaten zu identifizieren und zu lösen, oder ob Sie Zeit sparen und Anweisungen für eine größere Typenklasse hinzufügen möchten.  Hier ist das Hinzufügen von `dynamic`-Metadaten für `App.Core.ViewModels` möglicherweise der beste Ansatz, wenn die daraus resultierende Größenzunahme der Ausgabebinärdatei kein Problem ist.  
  
## <a name="could-the-code-be-rewritten"></a>Könnte der Code neu geschrieben werden?  
 Hätte die App `typeof(LayoutApplicationVM)` anstelle von `Type.GetType("LayoutApplicationVM")` verwendet, hätte die Toolkette `browse`-Metadaten beibehalten können.  Jedoch wären immer noch keine `invoke`-Metadaten erstellt worden, was zu einer [MissingMetadataException](missingmetadataexception-class-net-native.md)-Ausnahme beim Instanziieren des Typs geführt hätte. Um die Ausnahme zu verhindern, müssten Sie eine Laufzeitanweisung für den Namespace oder den Typ hinzufügen, der die `dynamic`-Richtlinie angibt. Informationen zu Laufzeitanweisungen finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei der Laufzeitanweisungen (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Erste Schritte](getting-started-with-net-native.md)
- [Beispiel: Behandeln von Ausnahmen beim Binden von Daten](example-handling-exceptions-when-binding-data.md)
