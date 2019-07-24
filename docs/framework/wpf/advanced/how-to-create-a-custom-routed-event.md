---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Routingereignisses'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], creating
- events [WPF], routing
ms.assetid: b79f459a-1c3f-4045-b2d4-1659cc8eaa3c
ms.openlocfilehash: cbfb88af4e35e3f090248982bb14d6b7a3a03cef
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401466"
---
# <a name="how-to-create-a-custom-routed-event"></a><span data-ttu-id="ea6b0-102">Vorgehensweise: Erstellen eines benutzerdefinierten Routingereignisses</span><span class="sxs-lookup"><span data-stu-id="ea6b0-102">How to: Create a Custom Routed Event</span></span>
<span data-ttu-id="ea6b0-103">Damit das benutzerdefinierte Ereignis das Ereignis Routing unterstützt, müssen Sie ein <xref:System.Windows.RoutedEvent> mit der <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> -Methode registrieren.</span><span class="sxs-lookup"><span data-stu-id="ea6b0-103">For your custom event to support event routing, you need to register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="ea6b0-104">Dieses Beispiel zeigt die Grundlagen der Erstellung eines benutzerdefinierten Routingereignisses.</span><span class="sxs-lookup"><span data-stu-id="ea6b0-104">This example demonstrates the basics of creating a custom routed event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea6b0-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ea6b0-105">Example</span></span>  
 <span data-ttu-id="ea6b0-106">Wie im folgenden Beispiel gezeigt, registrieren <xref:System.Windows.RoutedEvent> Sie zunächst mithilfe der <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> -Methode.</span><span class="sxs-lookup"><span data-stu-id="ea6b0-106">As shown in the following example, you first register a <xref:System.Windows.RoutedEvent> using the <xref:System.Windows.EventManager.RegisterRoutedEvent%2A> method.</span></span> <span data-ttu-id="ea6b0-107">Gemäß der Konvention sollte <xref:System.Windows.RoutedEvent> der statische Feldname mit dem Suffix- ***Ereignis***enden.</span><span class="sxs-lookup"><span data-stu-id="ea6b0-107">By convention, the <xref:System.Windows.RoutedEvent> static field name should end with the suffix ***Event***.</span></span> <span data-ttu-id="ea6b0-108">In diesem Beispiel ist `Tap` der Name des Ereignisses, und die Routing Strategie des Ereignisses ist. <xref:System.Windows.RoutingStrategy.Bubble></span><span class="sxs-lookup"><span data-stu-id="ea6b0-108">In this example, the name of the event is `Tap` and the routing strategy of the event is <xref:System.Windows.RoutingStrategy.Bubble>.</span></span> <span data-ttu-id="ea6b0-109">Nach dem Registrierungs Befehl können Sie Add-and-Remove Common Language Runtime (CLR)-Ereignisaccessoren für das Ereignis bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ea6b0-109">After the registration call, you can provide add-and-remove common language runtime (CLR) event accessors for the event.</span></span>  
  
 <span data-ttu-id="ea6b0-110">Beachten Sie, dass die Art, obwohl das Ereignis in diesem speziellen Beispiel über die virtuelle Methode `OnTap` ausgelöst wird, wie Sie das Ereignis auslösen oder wie Ihr Event auf Änderungen reagiert, von Ihren Anforderungen abhängt.</span><span class="sxs-lookup"><span data-stu-id="ea6b0-110">Note that even though the event is raised through the `OnTap` virtual method in this particular example, how you raise your event or how your event responds to changes depends on your needs.</span></span>  
  
 <span data-ttu-id="ea6b0-111">Beachten Sie auch, dass in diesem Beispiel grundsätzlich eine gesamte unter <xref:System.Windows.Controls.Button>Klasse von implementiert wird. Diese Unterklasse wird als separate Assembly erstellt und dann als benutzerdefinierte Klasse auf einer separaten [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Seite instanziiert.</span><span class="sxs-lookup"><span data-stu-id="ea6b0-111">Note also that this example basically implements an entire subclass of <xref:System.Windows.Controls.Button>; that subclass is built as a separate assembly and then instantiated as a custom class on a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] page.</span></span> <span data-ttu-id="ea6b0-112">Dadurch wird veranschaulicht, dass Steuerelemente als Unterklasse in Strukturen, die aus anderen Steuerelementen zusammengesetzt sind, eingefügt werden können, und in diesem Fall benutzerdefinierte Ereignisse dieser Steuerelemente über die gleichen Ereignisroutingfunktionen wie jedes native Element von [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] verfügen.</span><span class="sxs-lookup"><span data-stu-id="ea6b0-112">This is to illustrate the concept that subclassed controls can be inserted into trees composed of other controls, and that in this situation, custom events on these controls have the very same event routing capabilities as any native [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] element does.</span></span>  
  
 [!code-csharp[RoutedEventCustom#CustomClass](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/SDKSampleLibrary/class1.cs#customclass)]
 [!code-vb[RoutedEventCustom#CustomClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventCustom/VB/SDKSampleLibrary/Class1.vb#customclass)]  
  
 [!code-xaml[RoutedEventCustom#Page](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventCustom/CSharp/RoutedEventCustomApp/default.xaml#page)]  
  
 <span data-ttu-id="ea6b0-113">Tunnelingereignisse werden auf die gleiche Weise erstellt, wobei <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> jedoch im <xref:System.Windows.RoutingStrategy.Tunnel> Registrierungs Befehl auf festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ea6b0-113">Tunneling events are created the same way, but with <xref:System.Windows.RoutedEvent.RoutingStrategy%2A> set to <xref:System.Windows.RoutingStrategy.Tunnel> in the registration call.</span></span> <span data-ttu-id="ea6b0-114">In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] erhalten Tunneling-Ereignissen per Konvention das Wort „Preview“ als Präfix.</span><span class="sxs-lookup"><span data-stu-id="ea6b0-114">By convention, tunneling events in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] are prefixed with the word "Preview".</span></span>  
  
 <span data-ttu-id="ea6b0-115">Ein Beispiel der Funktionsweise des Bubbling von Ereignissen finden Sie unter [Behandeln eines Routingereignisses](how-to-handle-a-routed-event.md).</span><span class="sxs-lookup"><span data-stu-id="ea6b0-115">To see an example of how bubbling events work, see [Handle a Routed Event](how-to-handle-a-routed-event.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea6b0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea6b0-116">See also</span></span>

- [<span data-ttu-id="ea6b0-117">Übersicht über Routingereignisse</span><span class="sxs-lookup"><span data-stu-id="ea6b0-117">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="ea6b0-118">Übersicht über die Eingabe</span><span class="sxs-lookup"><span data-stu-id="ea6b0-118">Input Overview</span></span>](input-overview.md)
- [<span data-ttu-id="ea6b0-119">Übersicht über das Erstellen von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="ea6b0-119">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)
