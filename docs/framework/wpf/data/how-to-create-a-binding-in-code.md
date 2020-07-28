---
title: 'Gewusst wie: Erstellen einer Bindung in Code'
description: Erfahren Sie, wie Sie eine Bindung im Code in einer Windows Presentation Foundation Anwendung erstellen, indem Sie die SetBinding-Methode direkt aufrufen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: aa2a29f4c1262d8ac54641b856c297b284b23a38
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165811"
---
# <a name="how-to-create-a-binding-in-code"></a>Gewusst wie: Erstellen einer Bindung in Code
In diesem Beispiel wird gezeigt, wie ein im Code erstellt und festgelegt wird <xref:System.Windows.Data.Binding> .  
  
## <a name="example"></a>Beispiel  
 Die <xref:System.Windows.FrameworkElement> -Klasse und die- <xref:System.Windows.FrameworkContentElement> Klasse machen beide eine- `SetBinding` Methode verfügbar. Wenn Sie ein Element binden, das eine dieser Klassen erbt, können Sie die <xref:System.Windows.FrameworkElement.SetBinding%2A> Methode direkt aufzurufen.  
  
 Im folgenden Beispiel wird eine Klasse namens erstellt, `MyData` die eine Eigenschaft mit dem Namen enthält `MyDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#DataObject](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 Im folgenden Beispiel wird gezeigt, wie ein Bindungs Objekt erstellt wird, um die Quelle der Bindung festzulegen.  Im Beispiel wird verwendet, <xref:System.Windows.FrameworkElement.SetBinding%2A> um die- <xref:System.Windows.Controls.TextBlock.Text%2A> Eigenschaft von `myText` , die ein-Steuerelement ist <xref:System.Windows.Controls.TextBlock> , an zu binden `MyDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 Das Codebeispiel für den gesamten Code finden Sie unter Beispiel für reine [Code Bindung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771500(v=vs.90)).  
  
 Statt aufrufen <xref:System.Windows.FrameworkElement.SetBinding%2A> , können Sie die statische- <xref:System.Windows.Data.BindingOperations.SetBinding%2A> Methode der- <xref:System.Windows.Data.BindingOperations> Klasse verwenden. Im folgenden Beispiel wird <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> anstelle von aufgerufen, <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> um an zu binden `myText` `myDataProperty` .  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Datenbindung](../../../desktop-wpf/data/data-binding-overview.md)
- [Artikel zu Vorgehensweisen](data-binding-how-to-topics.md)
