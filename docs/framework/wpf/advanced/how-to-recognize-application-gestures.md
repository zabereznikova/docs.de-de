---
title: 'Vorgehensweise: Erkennen von Bewegungen in Anwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 68a7c8cd4b8ed935d005fabff37a7b44c1b98012
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506705"
---
# <a name="how-to-recognize-application-gestures"></a>Vorgehensweise: Erkennen von Bewegungen in Anwendungen
Das folgende Beispiel zeigt, wie Sie Freihandeingaben zu löschen, wenn ein Benutzer stellt eine <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> Gesten auf einem <xref:System.Windows.Controls.InkCanvas>. In diesem Beispiel geht davon aus einem <xref:System.Windows.Controls.InkCanvas>namens `inkCanvas1`, in der XAML-Datei deklariert wird.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[HowToRecognizeGestures#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Ink.ApplicationGesture>
- <xref:System.Windows.Controls.InkCanvas>
- <xref:System.Windows.Controls.InkCanvas.Gesture>
