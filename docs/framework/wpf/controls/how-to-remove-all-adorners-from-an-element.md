---
title: 'Gewusst wie: Entfernen aller Adorner aus einem Element'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 5b7e2038c8a314a180ba097a30c124f874c25893
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-remove-all-adorners-from-an-element"></a>Gewusst wie: Entfernen aller Adorner aus einem Element
In diesem Beispiel wird gezeigt, wie So entfernen Sie alle Adorner programmgesteuert aus einem angegebenen <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Beispiel  
 Diese ausführlichen Codebeispiel entfernt alle Adorner im Array von Adornern zurückgegebenes <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  In diesem Beispiel erfolgt, Abrufen von Adorner auf eine <xref:System.Windows.UIElement> mit dem Namen *MyTextBox*.  Wenn das Element im Aufruf angegeben <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> verfügt über keine Adorner `null` zurückgegeben wird.  Dieser Code überprüft, ob ein null-Array explizit und eignet sich optimal für Anwendungen, in denen ein null-Array erwartet wird, relativ häufig verwendet.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a>Beispiel  
 Dieser verkürzte Codebeispiel ist funktionell gleichwertig mit der oben gezeigten ausführlichen Beispiel. Dieser Code explizit überprüft nicht für ein null-Array, daher ist es möglich, eine <xref:System.NullReferenceException> Ausnahme kann ausgelöst werden.  Dieser Code eignet sich optimal für Anwendungen, in denen ist ein null-Array eher selten.  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Adorner](../../../../docs/framework/wpf/controls/adorners-overview.md)
