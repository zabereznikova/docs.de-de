---
title: 'Vorgehensweise: Implementieren von Validierungslogik für benutzerdefinierte Objekte'
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
ms.openlocfilehash: e2b77ef65c92ae596c5620c9122dcf3db0bf9462
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525988"
---
# <a name="how-to-implement-validation-logic-on-custom-objects"></a>Vorgehensweise: Implementieren von Validierungslogik für benutzerdefinierte Objekte
Dieses Beispiel veranschaulicht das Implementieren von Validierungslogik für ein benutzerdefiniertes Objekt, und klicken Sie dann an sie binden.  
  
## <a name="example"></a>Beispiel  
 Sie können auf der Geschäftsebene Validierungslogik bereitstellen, wenn das Quellobjekt implementiert <xref:System.ComponentModel.IDataErrorInfo>, wie im folgenden Beispiel definiert eine `Person` Objekt, das implementiert <xref:System.ComponentModel.IDataErrorInfo>:  
  
 [!code-csharp[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Data.cs#idataerrorinfo)]
 [!code-vb[BusinessLayerValidation#IDataErrorInfo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BusinessLayerValidation/VisualBasic/Data.vb#idataerrorinfo)]  
  
 Im folgenden Beispiel bindet die Text-Eigenschaft des Textfelds an die `Person.Age` -Eigenschaft, die für die Bindung über eine Ressourcendeklaration wurde die angegebenen die `x:Key` `data`. Die <xref:System.Windows.Controls.DataErrorValidationRule> von ausgelösten Fehler bei der Validierung überprüft, ob die <xref:System.ComponentModel.IDataErrorInfo> Implementierung.  
  
 [!code-xaml[BusinessLayerValidation#BoundTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BusinessLayerValidation/CSharp/Window1.xaml?highlight=8,11-19,25-42)]  
  
 Alternativ anstelle der <xref:System.Windows.Controls.DataErrorValidationRule>, Sie können festlegen, die <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> Eigenschaft, um `true`.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.ExceptionValidationRule>
- [Implementieren der Bindungsvalidierung](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)
- [Themen zu Vorgehensweisen](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
