---
title: 'Vorgehensweise: Überschreiben der logischen Struktur'
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: bf3459fff1a90326794d6713dd39c73596b0e960
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768445"
---
# <a name="how-to-override-the-logical-tree"></a><span data-ttu-id="80796-102">Vorgehensweise: Überschreiben der logischen Struktur</span><span class="sxs-lookup"><span data-stu-id="80796-102">How to: Override the Logical Tree</span></span>
<span data-ttu-id="80796-103">Obwohl es in den meisten Fällen nicht erforderlich ist, können erfahrene Autoren von Steuerelementen in der logischen Struktur überschreiben.</span><span class="sxs-lookup"><span data-stu-id="80796-103">Although it is not necessary in most cases, advanced control authors have the option to override the logical tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80796-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="80796-104">Example</span></span>  
 <span data-ttu-id="80796-105">In diesem Beispiel wird beschrieben, wie Sie die Unterklasse <xref:System.Windows.Controls.StackPanel> die logische Struktur in diesem Fall überschreiben, um ein Verhalten zu erzwingen, dass der Bereich kann nur und wird nur ein einzelnes untergeordnetes Element gerendert.</span><span class="sxs-lookup"><span data-stu-id="80796-105">This example describes how to subclass <xref:System.Windows.Controls.StackPanel> to override the logical tree, in this case to enforce a behavior that the panel may only have and will only render a single child element.</span></span> <span data-ttu-id="80796-106">Dieses Verhalten ist nicht unbedingt praktisch und erwünscht, aber es dient hier zur Veranschaulichung des Szenarios zum Überschreiben der normalen logischen Struktur eines Elements.</span><span class="sxs-lookup"><span data-stu-id="80796-106">This isn't necessarily a practically desirable behavior, but is shown here as a means of illustrating the scenario for overriding an element's normal logical tree.</span></span>  
  
 [!code-csharp[LogicalOverride#SingletonPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 <span data-ttu-id="80796-107">Weitere Informationen über die logische Struktur finden Sie unter [Strukturen in WPF](trees-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="80796-107">For more information on the logical tree, see [Trees in WPF](trees-in-wpf.md).</span></span>
