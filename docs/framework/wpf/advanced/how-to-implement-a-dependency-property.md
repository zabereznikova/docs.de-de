---
title: 'Vorgehensweise: Implementieren einer Abhängigkeitseigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 6f2fb9b0824feb6253527de063f58da2427d0c06
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400356"
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="35f2e-102">Vorgehensweise: Implementieren einer Abhängigkeitseigenschaft</span><span class="sxs-lookup"><span data-stu-id="35f2e-102">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="35f2e-103">In diesem Beispiel wird gezeigt, wie Sie eine Common Language Runtime (CLR)- <xref:System.Windows.DependencyProperty> Eigenschaft mit einem Feld sichern und so eine Abhängigkeits Eigenschaft definieren.</span><span class="sxs-lookup"><span data-stu-id="35f2e-103">This example shows how to back a common language runtime (CLR) property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="35f2e-104">Wenn Sie eigene Eigenschaften definieren und diese viele Aspekte der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Funktionalität unterstützen sollen, einschließlich Stile, Datenbindung, Vererbung, Animation und Standardwerte, müssen Sie sie als eine Abhängigkeitseigenschaft implementieren.</span><span class="sxs-lookup"><span data-stu-id="35f2e-104">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35f2e-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="35f2e-105">Example</span></span>  
 <span data-ttu-id="35f2e-106">Im folgenden Beispiel wird zuerst eine Abhängigkeits Eigenschaft durch Aufrufen <xref:System.Windows.DependencyProperty.Register%2A> der-Methode registriert.</span><span class="sxs-lookup"><span data-stu-id="35f2e-106">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="35f2e-107">Der Name des Bezeichnerfelds, das Sie verwenden, um den Namen und die Merkmale der Abhängigkeits Eigenschaft zu <xref:System.Windows.DependencyProperty.Name%2A> speichern, muss das sein, das Sie für die <xref:System.Windows.DependencyProperty.Register%2A> Abhängigkeits Eigenschaft als Teil des Aufrufens ausgewählt haben `Property`.</span><span class="sxs-lookup"><span data-stu-id="35f2e-107">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="35f2e-108">Wenn Sie beispielsweise eine Abhängigkeits Eigenschaft mit einem <xref:System.Windows.DependencyProperty.Name%2A> von `Location`registrieren, muss das Bezeichnerfeld, das Sie für die Abhängigkeits Eigenschaft definieren `LocationProperty`, benannt werden.</span><span class="sxs-lookup"><span data-stu-id="35f2e-108">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="35f2e-109">`State`In diesem Beispiel ist der Name der Abhängigkeits Eigenschaft und der zugehörige CLR-Accessor. Das Bezeichnerfeld ist `StateProperty`, der Typ der <xref:System.Boolean>Eigenschaft ist, und der Typ, der die Abhängigkeits Eigenschaft registriert, ist. `MyStateControl`</span><span class="sxs-lookup"><span data-stu-id="35f2e-109">In this example, the name of the dependency property and its CLR accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="35f2e-110">Wenn Sie dieses Benennungsmuster nicht befolgen, melden Designer Ihre Eigenschaft womöglich nicht ordnungsgemäß, und bestimmte Aspekte der Stilanwendung des Eigenschaftensystems verhalten sich möglicherweise anders als erwartet.</span><span class="sxs-lookup"><span data-stu-id="35f2e-110">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="35f2e-111">Sie können auch die standardmäßigen Metadaten für eine Abhängigkeitseigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="35f2e-111">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="35f2e-112">Dieses Beispiel registriert den Standardwert der `State`-Abhängigkeitseigenschaft als `false`.</span><span class="sxs-lookup"><span data-stu-id="35f2e-112">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="35f2e-113">Weitere Informationen darüber, wie und warum eine Abhängigkeits Eigenschaft implementiert wird, anstatt nur eine CLR-Eigenschaft mit einem privaten Feld zu unterstützen, finden Sie unter [Übersicht über Abhängigkeits Eigenschaften](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="35f2e-113">For more information about how and why to implement a dependency property, as opposed to just backing a CLR property with a private field, see [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35f2e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35f2e-114">See also</span></span>

- [<span data-ttu-id="35f2e-115">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="35f2e-115">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="35f2e-116">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="35f2e-116">How-to Topics</span></span>](properties-how-to-topics.md)
