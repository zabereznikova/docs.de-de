---
title: 'Vorgehensweise: Löschen von Bindungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bindings [WPF], clearing
- clearing bindings [WPF]
- data binding [WPF], clearing bindings
ms.assetid: 73962a93-32a9-4bcd-9240-bcfbb239093a
ms.openlocfilehash: 8bffc34864a2bf929bcbed09f16eac282e1ba2a5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360222"
---
# <a name="how-to-clear-bindings"></a>Vorgehensweise: Löschen von Bindungen
Dieses Beispiel zeigt, wie Bindungen aus einem Objekt gelöscht werden.  
  
## <a name="example"></a>Beispiel  
 Um eine Bindung aus einer einzelnen Eigenschaft für ein Objekt zu löschen, rufen <xref:System.Windows.Data.BindingOperations.ClearBinding%2A> wie im folgenden Beispiel gezeigt. Im folgenden Beispiel wird die Bindung aus der <xref:System.Windows.Controls.TextBlock.TextProperty> von *"MyText"*, <xref:System.Windows.Controls.TextBlock> Objekt.  
  
 [!code-csharp[CodeOnlyBinding#ClearBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#clearbinding)]
 [!code-vb[CodeOnlyBinding#ClearBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#clearbinding)]  
  
 Durch das Löschen einer Bindung wird diese entfernt, sodass die Abhängigkeitseigenschaft einen außerhalb der Bindung gültigen Wert annimmt. Dabei kann es sich um einen Standardwert, einen geerbten Wert oder um einen Wert aus einer Datenvorlagenbindung handeln.  
  
 Um Bindungen aus allen möglichen Eigenschaften eines Objekts zu löschen, verwenden <xref:System.Windows.Data.BindingOperations.ClearAllBindings%2A>.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Data.BindingOperations>
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
