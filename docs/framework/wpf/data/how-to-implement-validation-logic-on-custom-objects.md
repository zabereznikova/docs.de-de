---
title: 'Gewusst wie: Implementieren von Validierungslogik für benutzerdefinierte Objekte'
ms.date: 08/02/2018
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
ms.sourcegitcommit: 78bcb629abdbdbde0e295b4e81f350a477864aba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "33555963"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="b7bf6-102">Gewusst wie: Implementieren von Validierungslogik für benutzerdefinierte Objekte</span><span class="sxs-lookup"><span data-stu-id="b7bf6-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="b7bf6-103">Dieses Beispiel veranschaulicht das Implementieren von Validierungslogik für ein benutzerdefiniertes Objekt, und klicken Sie dann an sie binden.</span><span class="sxs-lookup"><span data-stu-id="b7bf6-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7bf6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7bf6-104">Example</span></span>  
 <span data-ttu-id="b7bf6-105">Sie können auf der Geschäftsebene Validierungslogik bereitstellen, wenn das Quellobjekt implementiert <xref:System.ComponentModel.IDataErrorInfo>, wie im folgenden Beispiel definiert eine `Person` Objekt, das implementiert <xref:System.ComponentModel.IDataErrorInfo>:</span><span class="sxs-lookup"><span data-stu-id="b7bf6-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example, which defines a `Person` object that implements <xref:System.ComponentModel.IDataErrorInfo>:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="b7bf6-106">Im folgenden Beispiel bindet die Text-Eigenschaft des Textfelds an die `Person.Age` -Eigenschaft, die für die Bindung über eine Ressourcendeklaration wurde die angegebenen die `x:Key` `data`.</span><span class="sxs-lookup"><span data-stu-id="b7bf6-106">In the following example, the text property of the text box binds to the `Person.Age` property, which has been made available for binding through a resource declaration that is given the `x:Key` `data`.</span></span> <span data-ttu-id="b7bf6-107">Die <xref:System.Windows.Controls.DataErrorValidationRule> von ausgelösten Fehler bei der Validierung überprüft, ob die <xref:System.ComponentModel.IDataErrorInfo> Implementierung.</span><span class="sxs-lookup"><span data-stu-id="b7bf6-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 <span data-ttu-id="b7bf6-108">Alternativ anstelle der <xref:System.Windows.Controls.DataErrorValidationRule>, Sie können festlegen, die <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> Eigenschaft, um `true`.</span><span class="sxs-lookup"><span data-stu-id="b7bf6-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7bf6-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7bf6-109">See Also</span></span>  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [<span data-ttu-id="b7bf6-110">Implementieren der Bindungsvalidierung</span><span class="sxs-lookup"><span data-stu-id="b7bf6-110">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="b7bf6-111">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="b7bf6-111">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
