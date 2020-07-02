---
title: Gruppen Steuerelemente mit GroupBox-Steuerelement
description: Erfahren Sie, wie Sie Steuerelemente mit dem Windows Forms GroupBox-Steuerelement gruppieren, sodass Sie eine visuelle Gruppierung verwandter Elemente erstellen können.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: f84c495a18f4ae5e04367f024a1e2849f1ed59f9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618063"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a>Vorgehensweise: Gruppieren von Steuerelementen mit dem GroupBox-Steuerelement in Windows Forms
Windows Forms-Steuer <xref:System.Windows.Forms.GroupBox> Elemente werden verwendet, um andere Steuerelemente zu gruppieren. Es gibt drei Gründe für das Gruppieren von Steuerelementen:  
  
- Zum Erstellen einer visuellen Gruppierung verwandter Formularelemente für eine eindeutige Benutzeroberfläche.  
  
- Zum Erstellen einer programmatischen Gruppierung (z. b. von Options Feldern).  
  
- Zum Verschieben der Steuerelemente als Einheit zur Entwurfszeit.  
  
### <a name="to-create-a-group-of-controls"></a>So erstellen Sie eine Gruppe von Steuerelementen  
  
1. Zeichnen Sie ein- <xref:System.Windows.Forms.GroupBox> Steuerelement in einem Formular.  
  
2. Fügen Sie dem Gruppenfeld weitere Steuerelemente hinzu, und zeichnen Sie die einzelnen Elemente innerhalb des Gruppen Felds.  
  
     Wenn Sie über vorhandene Steuerelemente verfügen, die Sie in ein Gruppenfeld einschließen möchten, können Sie alle Steuerelemente auswählen, Sie in die Zwischenablage Ausschneiden, das Steuerelement auswählen <xref:System.Windows.Forms.GroupBox> und dann in das Gruppenfeld einfügen. Sie können Sie auch in das Feld Gruppe ziehen.  
  
3. Legen Sie die- <xref:System.Windows.Forms.GroupBox.Text%2A> Eigenschaft des Gruppen Felds auf eine entsprechende Beschriftung fest.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.GroupBox>
- [GroupBox-Steuerelement](groupbox-control-windows-forms.md)
