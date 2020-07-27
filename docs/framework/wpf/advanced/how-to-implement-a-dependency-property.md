---
title: 'Gewusst wie: Implementieren einer Abhängigkeitseigenschaft'
description: Definieren Sie eine Abhängigkeits Eigenschaft in Windows Presentation Foundation, indem Sie eine Common Language Runtime Eigenschaft mit einem DependencyProperty-Feld unterstützen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dependency properties [WPF], backing properties with
- properties [WPF], backing with dependency properties
ms.assetid: 855fd6d7-19ac-493c-bf5e-2f40b57cdc92
ms.openlocfilehash: 673f653a9b02627efcccdfe08c4812ca0834217c
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165097"
---
# <a name="how-to-implement-a-dependency-property"></a><span data-ttu-id="0839d-103">Gewusst wie: Implementieren einer Abhängigkeitseigenschaft</span><span class="sxs-lookup"><span data-stu-id="0839d-103">How to: Implement a Dependency Property</span></span>
<span data-ttu-id="0839d-104">In diesem Beispiel wird gezeigt, wie Sie eine Common Language Runtime (CLR)-Eigenschaft mit einem <xref:System.Windows.DependencyProperty> Feld sichern und so eine Abhängigkeits Eigenschaft definieren.</span><span class="sxs-lookup"><span data-stu-id="0839d-104">This example shows how to back a common language runtime (CLR) property with a <xref:System.Windows.DependencyProperty> field, thus defining a dependency property.</span></span> <span data-ttu-id="0839d-105">Wenn Sie eigene Eigenschaften definieren und diese viele Aspekte der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Funktionalität unterstützen sollen, einschließlich Stile, Datenbindung, Vererbung, Animation und Standardwerte, müssen Sie sie als eine Abhängigkeitseigenschaft implementieren.</span><span class="sxs-lookup"><span data-stu-id="0839d-105">When you define your own properties and want them to support many aspects of [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] functionality, including styles, data binding, inheritance, animation, and default values, you should implement them as a dependency property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0839d-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0839d-106">Example</span></span>  
 <span data-ttu-id="0839d-107">Im folgenden Beispiel wird zuerst eine Abhängigkeits Eigenschaft durch Aufrufen der- <xref:System.Windows.DependencyProperty.Register%2A> Methode registriert.</span><span class="sxs-lookup"><span data-stu-id="0839d-107">The following example first registers a dependency property by calling the <xref:System.Windows.DependencyProperty.Register%2A> method.</span></span> <span data-ttu-id="0839d-108">Der Name des Bezeichnerfelds, das Sie verwenden, um den Namen und die Merkmale der Abhängigkeits Eigenschaft zu speichern, muss das sein <xref:System.Windows.DependencyProperty.Name%2A> , das Sie für die Abhängigkeits Eigenschaft als Teil des <xref:System.Windows.DependencyProperty.Register%2A> Aufrufens ausgewählt haben `Property` .</span><span class="sxs-lookup"><span data-stu-id="0839d-108">The name of the identifier field that you use to store the name and characteristics of the dependency property must be the <xref:System.Windows.DependencyProperty.Name%2A> you chose for the dependency property as part of the <xref:System.Windows.DependencyProperty.Register%2A> call, appended by the literal string `Property`.</span></span> <span data-ttu-id="0839d-109">Wenn Sie beispielsweise eine Abhängigkeits Eigenschaft mit einem <xref:System.Windows.DependencyProperty.Name%2A> von registrieren `Location` , muss das Bezeichnerfeld, das Sie für die Abhängigkeits Eigenschaft definieren, benannt werden `LocationProperty` .</span><span class="sxs-lookup"><span data-stu-id="0839d-109">For instance, if you register a dependency property with a <xref:System.Windows.DependencyProperty.Name%2A> of `Location`, then the identifier field that you define for the dependency property must be named `LocationProperty`.</span></span>  
  
 <span data-ttu-id="0839d-110">In diesem Beispiel ist der Name der Abhängigkeits Eigenschaft und der zugehörige CLR-Accessor `State` . Das Bezeichnerfeld ist, `StateProperty` der Typ der Eigenschaft ist, <xref:System.Boolean> und der Typ, der die Abhängigkeits Eigenschaft registriert, ist `MyStateControl` .</span><span class="sxs-lookup"><span data-stu-id="0839d-110">In this example, the name of the dependency property and its CLR accessor is `State`; the identifier field is `StateProperty`; the type of the property is <xref:System.Boolean>; and the type that registers the dependency property is `MyStateControl`.</span></span>  
  
 <span data-ttu-id="0839d-111">Wenn Sie dieses Benennungsmuster nicht befolgen, melden Designer Ihre Eigenschaft womöglich nicht ordnungsgemäß, und bestimmte Aspekte der Stilanwendung des Eigenschaftensystems verhalten sich möglicherweise anders als erwartet.</span><span class="sxs-lookup"><span data-stu-id="0839d-111">If you fail to follow this naming pattern, designers might not report your property correctly, and certain aspects of property system style application might not behave as expected.</span></span>  
  
 <span data-ttu-id="0839d-112">Sie können auch die standardmäßigen Metadaten für eine Abhängigkeitseigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="0839d-112">You can also specify default metadata for a dependency property.</span></span> <span data-ttu-id="0839d-113">Dieses Beispiel registriert den Standardwert der `State`-Abhängigkeitseigenschaft als `false`.</span><span class="sxs-lookup"><span data-stu-id="0839d-113">This example registers the default value of the `State` dependency property to be `false`.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
  
 <span data-ttu-id="0839d-114">Weitere Informationen darüber, wie und warum eine Abhängigkeits Eigenschaft implementiert wird, anstatt nur eine CLR-Eigenschaft mit einem privaten Feld zu unterstützen, finden Sie unter [Übersicht über Abhängigkeits Eigenschaften](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0839d-114">For more information about how and why to implement a dependency property, as opposed to just backing a CLR property with a private field, see [Dependency Properties Overview](dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0839d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0839d-115">See also</span></span>

- [<span data-ttu-id="0839d-116">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="0839d-116">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="0839d-117">Artikel zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="0839d-117">How-to Topics</span></span>](properties-how-to-topics.md)
