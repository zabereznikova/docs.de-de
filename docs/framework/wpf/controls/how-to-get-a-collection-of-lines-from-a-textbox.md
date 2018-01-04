---
title: 'Gewusst wie: Abrufen einer Auflistung der Zeilen aus einem "TextBox"-Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12d32266bb901f6ce47d19d92d6f0785277aa7c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a>Gewusst wie: Abrufen einer Auflistung der Zeilen aus einem "TextBox"-Element
In diesem Beispiel wird gezeigt, wie eine Auflistung von Textzeilen aus Abrufen einer <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine einfache Methode, die eine <xref:System.Windows.Controls.TextBox> als Argument und gibt eine <xref:System.Collections.Specialized.StringCollection> , enthält die Textzeilen in die **Textfeld**.  Die <xref:System.Windows.Controls.TextBox.LineCount%2A> Eigenschaft wird verwendet, um zu bestimmen, wie viele Zeilen derzeit sind die **Textfeld**, und die <xref:System.Windows.Controls.TextBox.GetLineText%2A> Methode wird zum Extrahieren des jede Zeile, und fügen es auf die Auflistung von Zeilen verwendet.  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Übersicht über RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
