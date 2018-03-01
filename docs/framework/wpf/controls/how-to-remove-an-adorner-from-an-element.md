---
title: 'Gewusst wie: Entfernen eines Adorners aus einem Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 20d17ef43f99f6815334c0acbf7eb2040959751e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-an-adorner-from-an-element"></a>Gewusst wie: Entfernen eines Adorners aus einem Element
In diesem Beispiel wird gezeigt, wie So entfernen Sie einen bestimmten Adorner programmgesteuert aus einem angegebenen <xref:System.Windows.UIElement>.  
  
## <a name="example"></a>Beispiel  
 Dieses Codebeispiel ausführliche entfernt ersten Funktionsindikator im Array von Adornern zurückgegebenes <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.  In diesem Beispiel erfolgt, Abrufen von Adorner auf eine <xref:System.Windows.UIElement> mit dem Namen *MyTextBox*.  Wenn das Element im Aufruf angegeben <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> verfügt über keine Adorner `null` zurückgegeben wird.  Dieser Code überprüft, ob ein null-Array explizit und eignet sich optimal für Anwendungen, in denen ein null-Array erwartet wird, relativ häufig verwendet.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a>Beispiel  
 Dieser verkürzte Codebeispiel ist funktionell gleichwertig mit der oben gezeigten ausführlichen Beispiel. Dieser Code explizit überprüft nicht für ein null-Array, daher ist es möglich, eine <xref:System.NullReferenceException> Ausnahme kann ausgelöst werden.  Dieser Code eignet sich optimal für Anwendungen, in denen ist ein null-Array eher selten.  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Adorner](../../../../docs/framework/wpf/controls/adorners-overview.md)
