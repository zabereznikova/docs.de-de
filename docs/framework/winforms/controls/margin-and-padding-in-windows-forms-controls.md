---
title: Margin und Padding in Steuerelementen
description: Erfahren Sie, wie Sie mit den Rand-und paddingeigenschaften Ränder und Auffüll Zeichen in Windows Form-Steuerelementen hinzufügen.
ms.date: 03/30/2017
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
ms.openlocfilehash: 4279f39bb4f89fbda8be472f49c8e60853abcac6
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174483"
---
# <a name="margin-and-padding-in-windows-forms-controls"></a>Rand und Abstand in Windows Forms-Steuerelementen
Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert. Der <xref:System.Windows.Forms?displayProperty=nameWithType>-Namespace bietet Ihnen hierfür zahlreiche Layoutfunktionen. Zwei der wichtigsten Funktionen sind die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft.  
  
 Die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft definiert den Bereich um das Steuerelement, durch den andere Steuerelemente einen bestimmten Abstand von den Rändern des Steuerelements einhalten müssen.  
  
 Die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft definiert den Bereich innerhalb eines Steuerelements, durch den der Inhalt des Steuerelements (z. B. der Wert seiner <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft) einen bestimmten Abstand von den Rändern des Steuerelements einhalten muss.  
  
 Die folgende Abbildung zeigt die <xref:System.Windows.Forms.Control.Padding%2A>-Eigenschaft und die <xref:System.Windows.Forms.Control.Margin%2A>-Eigenschaft für ein Steuerelement.  
  
 ![Ränder und Abstände bei Windows Forms-Steuerelementen](./media/vs-winformpadmargin.gif "VS_WinFormPadMargin")  
  
 Diese Funktion wird zur Entwurfszeit in Visual Studio unterstützt. Siehe auch Exemplarische Vorgehensweise: Anordnen [von Windows Forms-Steuerelementen mit Auffüll Zeichen, Rändern und der AutoSize-Eigenschaft](windows-forms-controls-padding-autosize.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.Margin%2A>
- <xref:System.Windows.Forms.Control.Padding%2A>
- <xref:System.Windows.Forms.Control.LayoutEngine%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
