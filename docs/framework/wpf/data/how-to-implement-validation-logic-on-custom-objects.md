---
title: 'Gewusst wie: Implementieren von Validierungslogik für benutzerdefinierte Objekte'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
ms.openlocfilehash: dbeddb5eb6996d5758717ddd2d4d5af0b6f57f3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555963"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="66eb0-102">Gewusst wie: Implementieren von Validierungslogik für benutzerdefinierte Objekte</span><span class="sxs-lookup"><span data-stu-id="66eb0-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="66eb0-103">In diesem Beispiel veranschaulicht das Implementieren von Validierungslogik für ein benutzerdefiniertes Objekt, und klicken Sie dann darauf binden.</span><span class="sxs-lookup"><span data-stu-id="66eb0-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66eb0-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66eb0-104">Example</span></span>  
 <span data-ttu-id="66eb0-105">Sie können Validierungslogik auf der Geschäftsebene bereitstellen, wenn das Quellobjekt implementiert <xref:System.ComponentModel.IDataErrorInfo>, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="66eb0-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="66eb0-106">Im folgenden Beispiel bindet die Texteigenschaft des Textfelds an die `Age` Eigenschaft von der `Person` -Objekt, das Bindung über eine Ressource zur vorgenommen wurde, die angegeben wird die `x:Key``data`.</span><span class="sxs-lookup"><span data-stu-id="66eb0-106">In the following example, the text property of the text box binds to the `Age` property of the `Person` object, which has been made available for binding through a resource declaration that is given the `x:Key``data`.</span></span> <span data-ttu-id="66eb0-107">Die <xref:System.Windows.Controls.DataErrorValidationRule> überprüft, ob die Validierungsfehler, die ausgelöst wird, indem Sie die <xref:System.ComponentModel.IDataErrorInfo> Implementierung.</span><span class="sxs-lookup"><span data-stu-id="66eb0-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 <span data-ttu-id="66eb0-108">Alternativ können Sie anstelle der <xref:System.Windows.Controls.DataErrorValidationRule>, Sie können festlegen, die <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> Eigenschaft, um `true`.</span><span class="sxs-lookup"><span data-stu-id="66eb0-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66eb0-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66eb0-109">See Also</span></span>  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [<span data-ttu-id="66eb0-110">Implementieren der Bindungsvalidierung</span><span class="sxs-lookup"><span data-stu-id="66eb0-110">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="66eb0-111">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="66eb0-111">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
