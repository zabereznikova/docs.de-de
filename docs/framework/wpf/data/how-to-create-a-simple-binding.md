---
title: 'Gewusst wie: Erstellen einer einfachen Bindung'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: faef59ed426059eb2d488d0584d3325c8d46d415
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453507"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="99494-102">Gewusst wie: Erstellen einer einfachen Bindung</span><span class="sxs-lookup"><span data-stu-id="99494-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="99494-103">In diesem Beispiel wird gezeigt, wie ein einfaches <xref:System.Windows.Data.Binding>erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="99494-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99494-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="99494-104">Example</span></span>  
 <span data-ttu-id="99494-105">In diesem Beispiel verfügen Sie über ein `Person`-Objekt mit einer Zeichen folgen Eigenschaft namens `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="99494-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="99494-106">Das `Person`-Objekt wird im Namespace mit dem Namen `SDKSample`definiert.</span><span class="sxs-lookup"><span data-stu-id="99494-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="99494-107">Die hervorgehobene Zeile, die das `<src>` Element im folgenden Beispiel enthält, instanziiert das `Person`-Objekt mit dem `PersonName`-Eigenschafts Wert `Joe`.</span><span class="sxs-lookup"><span data-stu-id="99494-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="99494-108">Dies erfolgt im `Resources` Abschnitt, und es wurde ein `x:Key`zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="99494-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="99494-109">Die markierte Zeile, die das `<TextBlock>` Element enthält, bindet dann das <xref:System.Windows.Controls.TextBlock>-Steuerelement an die `PersonName`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="99494-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="99494-110">Folglich wird die <xref:System.Windows.Controls.TextBlock> mit dem Wert "Joe" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="99494-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99494-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99494-111">See also</span></span>

- [<span data-ttu-id="99494-112">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="99494-112">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="99494-113">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="99494-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
