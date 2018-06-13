---
title: 'Gewusst wie: Erkennen von Bewegungen in Anwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 82ca91fc9e3745012d82357991b67f398079f1f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543692"
---
# <a name="how-to-recognize-application-gestures"></a><span data-ttu-id="47bc7-102">Gewusst wie: Erkennen von Bewegungen in Anwendungen</span><span class="sxs-lookup"><span data-stu-id="47bc7-102">How To: Recognize Application Gestures</span></span>
<span data-ttu-id="47bc7-103">Im folgenden Beispiel wird veranschaulicht, wie Freihandeingaben gelöscht, wenn ein Benutzer sendet eine <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> Gestenhandler auf einem <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="47bc7-103">The following example demonstrates how to erase ink when a user makes a <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> gesture on an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="47bc7-104">In diesem Beispiel geht davon aus einer <xref:System.Windows.Controls.InkCanvas>namens `inkCanvas1`, der in der XAML-Datei deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="47bc7-104">This example assumes an <xref:System.Windows.Controls.InkCanvas>, called `inkCanvas1`, is declared in the XAML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47bc7-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="47bc7-105">Example</span></span>  
 [!code-csharp[HowToRecognizeGestures#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="47bc7-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47bc7-106">See Also</span></span>  
 <xref:System.Windows.Ink.ApplicationGesture>  
 <xref:System.Windows.Controls.InkCanvas>  
 <xref:System.Windows.Controls.InkCanvas.Gesture>
