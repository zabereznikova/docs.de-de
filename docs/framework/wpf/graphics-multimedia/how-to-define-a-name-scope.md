---
title: 'Vorgehensweise: Definieren eines Namensbereichs'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: a03f477dd31909e8cb9dde9cd29da6f38d665758
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086818"
---
# <a name="how-to-define-a-name-scope"></a><span data-ttu-id="fa7f7-102">Vorgehensweise: Definieren eines Namensbereichs</span><span class="sxs-lookup"><span data-stu-id="fa7f7-102">How to: Define a Name Scope</span></span>
<span data-ttu-id="fa7f7-103">Animieren mit <xref:System.Windows.Media.Animation.Storyboard> im Code müssen Sie erstellen eine <xref:System.Windows.NameScope> und registrieren Sie die Namen der Zielobjekte mit dem Element, das diesen Namensbereich besitzt.</span><span class="sxs-lookup"><span data-stu-id="fa7f7-103">To animate with <xref:System.Windows.Media.Animation.Storyboard> in code, you must create a <xref:System.Windows.NameScope> and register the target objects' names with the element that owns that name scope.</span></span> <span data-ttu-id="fa7f7-104">Im folgenden Beispiel eine <xref:System.Windows.NameScope> für erstellt `myMainPanel`.</span><span class="sxs-lookup"><span data-stu-id="fa7f7-104">In the following example, a <xref:System.Windows.NameScope> is created for `myMainPanel`.</span></span> <span data-ttu-id="fa7f7-105">Zwei Schaltflächen, `button1` und `button2`, Bereich, und ihre registrierten Namen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fa7f7-105">Two buttons, `button1` and `button2`, are added to the panel, and their names registered.</span></span> <span data-ttu-id="fa7f7-106">Mehrere Animationen und <xref:System.Windows.Media.Animation.Storyboard> werden erstellt.</span><span class="sxs-lookup"><span data-stu-id="fa7f7-106">Several animations and a <xref:System.Windows.Media.Animation.Storyboard> are created.</span></span> <span data-ttu-id="fa7f7-107">Storyboard <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode wird verwendet, um die Animationen zu starten.</span><span class="sxs-lookup"><span data-stu-id="fa7f7-107">The storyboard's <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method is used to start the animations.</span></span>  
  
 <span data-ttu-id="fa7f7-108">Da `button1`, `button2`, und `myMainPanel` all den Gültigkeitsbereich der gleichen Namen verwenden, eines dieser Projekte kann verwendet werden, mit der <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> Methode, um die Animationen zu starten.</span><span class="sxs-lookup"><span data-stu-id="fa7f7-108">Because `button1`, `button2`, and `myMainPanel` all share the same name scope, any one of them can be used with the <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method to start the animations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa7f7-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa7f7-109">Example</span></span>  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="fa7f7-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa7f7-110">See also</span></span>

- [<span data-ttu-id="fa7f7-111">Animieren einer Eigenschaft unter Verwendung eines Storyboards</span><span class="sxs-lookup"><span data-stu-id="fa7f7-111">Animate a Property by Using a Storyboard</span></span>](how-to-animate-a-property-by-using-a-storyboard.md)
- [<span data-ttu-id="fa7f7-112">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="fa7f7-112">Animation Overview</span></span>](animation-overview.md)
