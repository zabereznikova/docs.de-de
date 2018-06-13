---
title: 'Gewusst wie: Überschreiben der logischen Struktur'
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: 0c7269b9ea052019e2e4f6def23b063903cbb5e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542889"
---
# <a name="how-to-override-the-logical-tree"></a><span data-ttu-id="068f9-102">Gewusst wie: Überschreiben der logischen Struktur</span><span class="sxs-lookup"><span data-stu-id="068f9-102">How to: Override the Logical Tree</span></span>
<span data-ttu-id="068f9-103">Obwohl es in den meisten Fällen nicht erforderlich ist, können erfahrene Autoren von Steuerelementen in der logischen Struktur überschreiben.</span><span class="sxs-lookup"><span data-stu-id="068f9-103">Although it is not necessary in most cases, advanced control authors have the option to override the logical tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="068f9-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="068f9-104">Example</span></span>  
 <span data-ttu-id="068f9-105">In diesem Beispiel wird beschrieben, wie Sie Unterklasse <xref:System.Windows.Controls.StackPanel> die logische Struktur in diesem Fall überschreiben, um ein Verhalten zu erzwingen, dass der Bereich nur enthalten sein darf und wird nur ein einzelnes untergeordnetes Element gerendert.</span><span class="sxs-lookup"><span data-stu-id="068f9-105">This example describes how to subclass <xref:System.Windows.Controls.StackPanel> to override the logical tree, in this case to enforce a behavior that the panel may only have and will only render a single child element.</span></span> <span data-ttu-id="068f9-106">Dieses Verhalten ist nicht unbedingt praktisch und erwünscht, aber es dient hier zur Veranschaulichung des Szenarios zum Überschreiben der normalen logischen Struktur eines Elements.</span><span class="sxs-lookup"><span data-stu-id="068f9-106">This isn't necessarily a practically desirable behavior, but is shown here as a means of illustrating the scenario for overriding an element's normal logical tree.</span></span>  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 <span data-ttu-id="068f9-107">Weitere Informationen über die logische Struktur finden Sie unter [Strukturen in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="068f9-107">For more information on the logical tree, see [Trees in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).</span></span>
