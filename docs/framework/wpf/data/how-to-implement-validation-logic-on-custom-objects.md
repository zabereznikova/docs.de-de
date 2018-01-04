---
title: "Gewusst wie: Implementieren von Validierungslogik für benutzerdefinierte Objekte"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- checking for validation errors [WPF]
- validation errors [WPF], checking for
- implementing validation logic on custom objects [WPF]
- custom objects [WPF], implementing validation logic on
ms.assetid: 751fda9b-44f9-4d63-b4f2-1df07ac41e0f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5044339e1d06bddad05151b2db99d5f96d068e77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a><span data-ttu-id="adba2-102">Gewusst wie: Implementieren von Validierungslogik für benutzerdefinierte Objekte</span><span class="sxs-lookup"><span data-stu-id="adba2-102">How to: Implement Validation Logic on Custom Objects</span></span>
<span data-ttu-id="adba2-103">In diesem Beispiel veranschaulicht das Implementieren von Validierungslogik für ein benutzerdefiniertes Objekt, und klicken Sie dann darauf binden.</span><span class="sxs-lookup"><span data-stu-id="adba2-103">This example shows how to implement validation logic on a custom object and then bind to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adba2-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="adba2-104">Example</span></span>  
 <span data-ttu-id="adba2-105">Sie können Validierungslogik auf der Geschäftsebene bereitstellen, wenn das Quellobjekt implementiert <xref:System.ComponentModel.IDataErrorInfo>, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="adba2-105">You can provide validation logic on the business layer if your source object implements <xref:System.ComponentModel.IDataErrorInfo>, as in the following example:</span></span>  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 <span data-ttu-id="adba2-106">Im folgenden Beispiel bindet die Texteigenschaft des Textfelds an die `Age` Eigenschaft von der `Person` -Objekt, das Bindung über eine Ressource zur vorgenommen wurde, die angegeben wird die `x:Key``data`.</span><span class="sxs-lookup"><span data-stu-id="adba2-106">In the following example, the text property of the text box binds to the `Age` property of the `Person` object, which has been made available for binding through a resource declaration that is given the `x:Key``data`.</span></span> <span data-ttu-id="adba2-107">Die <xref:System.Windows.Controls.DataErrorValidationRule> überprüft, ob die Validierungsfehler, die ausgelöst wird, indem Sie die <xref:System.ComponentModel.IDataErrorInfo> Implementierung.</span><span class="sxs-lookup"><span data-stu-id="adba2-107">The <xref:System.Windows.Controls.DataErrorValidationRule> checks for the validation errors raised by the <xref:System.ComponentModel.IDataErrorInfo> implementation.</span></span>  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 <span data-ttu-id="adba2-108">Alternativ können Sie anstelle der <xref:System.Windows.Controls.DataErrorValidationRule>, Sie können festlegen, die <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> Eigenschaft, um `true`.</span><span class="sxs-lookup"><span data-stu-id="adba2-108">Alternatively, instead of using the <xref:System.Windows.Controls.DataErrorValidationRule>, you can set the <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adba2-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="adba2-109">See Also</span></span>  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [<span data-ttu-id="adba2-110">Implementieren der Bindungsvalidierung</span><span class="sxs-lookup"><span data-stu-id="adba2-110">Implement Binding Validation</span></span>](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [<span data-ttu-id="adba2-111">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="adba2-111">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
