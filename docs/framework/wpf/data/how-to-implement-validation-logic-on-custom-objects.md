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
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>Gewusst wie: Implementieren von Validierungslogik für benutzerdefinierte Objekte
In diesem Beispiel veranschaulicht das Implementieren von Validierungslogik für ein benutzerdefiniertes Objekt, und klicken Sie dann darauf binden.  
  
## <a name="example"></a>Beispiel  
 Sie können Validierungslogik auf der Geschäftsebene bereitstellen, wenn das Quellobjekt implementiert <xref:System.ComponentModel.IDataErrorInfo>, wie im folgenden Beispiel:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 Im folgenden Beispiel bindet die Texteigenschaft des Textfelds an die `Age` Eigenschaft von der `Person` -Objekt, das Bindung über eine Ressource zur vorgenommen wurde, die angegeben wird die `x:Key``data`. Die <xref:System.Windows.Controls.DataErrorValidationRule> überprüft, ob die Validierungsfehler, die ausgelöst wird, indem Sie die <xref:System.ComponentModel.IDataErrorInfo> Implementierung.  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml#boundtextbox)]  
  
 Alternativ können Sie anstelle der <xref:System.Windows.Controls.DataErrorValidationRule>, Sie können festlegen, die <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> Eigenschaft, um `true`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.ExceptionValidationRule>  
 [Implementieren der Bindungsvalidierung](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)  
 [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
