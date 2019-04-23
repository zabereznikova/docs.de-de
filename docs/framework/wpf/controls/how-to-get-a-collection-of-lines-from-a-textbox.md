---
title: 'Vorgehensweise: Abrufen einer Auflistung der Zeilen aus einem TextBox-Objekt'
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: b7b2f1c2e071388635fb50b1e3573fd7f44334dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224636"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a>Vorgehensweise: Abrufen einer Auflistung der Zeilen aus einem TextBox-Objekt
In diesem Beispiel wird gezeigt, wie zum Abrufen einer Auflistung von Textzeilen aus einer <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine einfache Methode, die eine <xref:System.Windows.Controls.TextBox> als Argument und gibt eine <xref:System.Collections.Specialized.StringCollection> , enthält die Textzeilen in der **Textfeld**.  Die <xref:System.Windows.Controls.TextBox.LineCount%2A> Eigenschaft wird verwendet, um zu bestimmen, wie viele Zeilen zurzeit sind die **Textfeld**, und die <xref:System.Windows.Controls.TextBox.GetLineText%2A> -Methode wird anschließend verwendet, können Sie jede Zeile zu extrahieren und auf die Auflistung von Zeilen hinzufügen.  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über TextBox](textbox-overview.md)
- [Übersicht über RichTextBox](richtextbox-overview.md)
