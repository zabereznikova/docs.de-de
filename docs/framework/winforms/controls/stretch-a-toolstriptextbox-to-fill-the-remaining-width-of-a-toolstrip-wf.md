---
title: 'Gewusst wie: Strecken einer ToolStripTextBox zum Ausfüllen der verbleibenden Breite eines ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: c60cc2a377f08a73159f25b2ab5f2812d41f0c10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742838"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a>Gewusst wie: Strecken einer ToolStripTextBox zum Ausfüllen der verbleibenden Breite eines ToolStrip (Windows Forms)
Wenn Sie die <xref:System.Windows.Forms.ToolStrip.Stretch%2A>-Eigenschaft eines <xref:System.Windows.Forms.ToolStrip>-Steuer Elements auf `true`festlegen, füllt das Steuerelement seinen Container von End-to-End aus und ändert seine Größe, wenn die Größe des Containers geändert wird. In dieser Konfiguration ist es möglicherweise sinnvoll, ein Element im Steuerelement, z. b. eine <xref:System.Windows.Forms.ToolStripTextBox>, zu Strecken, um den verfügbaren Platz auszufüllen und die Größe zu ändern, wenn die Größe des Steuer Elements geändert wird. Diese Streckung ist beispielsweise nützlich, wenn Sie aussehen und Verhalten ähnlich der Adressleiste in Microsoft® Internet Explorer erreichen möchten.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel stellt eine Klasse bereit, die von <xref:System.Windows.Forms.ToolStripTextBox> namens `ToolStripSpringTextBox`abgeleitet ist. Diese Klasse überschreibt die <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A>-Methode, um die verfügbare Breite des übergeordneten <xref:System.Windows.Forms.ToolStrip> Steuer Elements zu berechnen, nachdem die kombinierte Breite aller anderen Elemente subtrahiert wurde. Dieses Codebeispiel bietet auch eine <xref:System.Windows.Forms.Form>-Klasse und eine `Program`-Klasse, um das neue Verhalten zu veranschaulichen.  
  
 [!code-csharp[ToolStripSpringTextBox#00](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripTextBox>
- <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>
- [Architektur des ToolStrip-Steuerelements](toolstrip-control-architecture.md)
- [Gewusst wie: Interaktive Verwendung der Spring-Eigenschaft in StatusStrip](how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
