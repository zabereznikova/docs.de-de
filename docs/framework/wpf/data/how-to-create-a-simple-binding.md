---
title: 'Vorgehensweise: Erstellen von einfachen Bindungen'
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 157060e784e4169ac8e31c6028ed65f0a9568e0f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373581"
---
# <a name="how-to-create-a-simple-binding"></a><span data-ttu-id="a55fd-102">Vorgehensweise: Erstellen von einfachen Bindungen</span><span class="sxs-lookup"><span data-stu-id="a55fd-102">How to: Create a Simple Binding</span></span>
<span data-ttu-id="a55fd-103">Dieses Beispiel zeigt, wie zum Erstellen eines einfachen <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="a55fd-103">This example shows you how to create a simple <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a55fd-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a55fd-104">Example</span></span>  
 <span data-ttu-id="a55fd-105">In diesem Beispiel verfügen Sie über eine `Person` Objekt mit einer Zeichenfolgeneigenschaft, die mit dem Namen `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="a55fd-105">In this example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="a55fd-106">Die `Person` Objekt wird definiert, in dem Namespace namens `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="a55fd-106">The `Person` object is defined in the namespace called `SDKSample`.</span></span>  
  
 <span data-ttu-id="a55fd-107">Die hervorgehobene Zeile mit der `<src>` Element im folgenden Beispiel instanziiert die `Person` Objekt mit einer `PersonName` Eigenschaftswert `Joe`.</span><span class="sxs-lookup"><span data-stu-id="a55fd-107">The highlighted line that contains the `<src>` element in the following example instantiates the `Person` object with a `PersonName` property value of `Joe`.</span></span> <span data-ttu-id="a55fd-108">Dies erfolgt in der `Resources` Abschnitt zugewiesen, und wählen Sie eine `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="a55fd-108">This is done in the `Resources` section and assigned an `x:Key`.</span></span>  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="a55fd-109">Die hervorgehobene Zeile mit der `<TextBlock>` -Element bindet dann die <xref:System.Windows.Controls.TextBlock> die Steuerung an die `PersonName` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a55fd-109">The highlighted line that contains the `<TextBlock>` element then binds the <xref:System.Windows.Controls.TextBlock> control to the `PersonName` property.</span></span> <span data-ttu-id="a55fd-110">Daher die <xref:System.Windows.Controls.TextBlock> mit dem Wert "Joe" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a55fd-110">As a result, the <xref:System.Windows.Controls.TextBlock> appears with the value "Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a55fd-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a55fd-111">See also</span></span>
- [<span data-ttu-id="a55fd-112">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="a55fd-112">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="a55fd-113">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="a55fd-113">How-to Topics</span></span>](data-binding-how-to-topics.md)
