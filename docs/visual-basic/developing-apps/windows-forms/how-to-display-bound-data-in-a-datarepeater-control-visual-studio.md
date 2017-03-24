---
title: 'Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement (Visual Studio) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, data-binding
- DataRepeater, displaying bound controls
ms.assetid: 56a15326-1334-4275-af4e-075cad79e6f7
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9bf8f2f5fcc4dfa2b29e368a4e26bf112e08149e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-display-bound-data-in-a-datarepeater-control-visual-studio"></a>Gewusst wie: Anzeigen von gebundenen Daten in einem DataRepeater-Steuerelement (Visual Studio)
Die häufigste Verwendung von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement gebundene Daten aus einer Datenbank oder anderen Datenquelle angezeigt wird.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
 Zusätzlich zu den gebundenen Steuerelementen sollten andere Steuerelemente hinzufügen, z. B. eine statische Bezeichnung oder ein Bild, das wiederholt wird, für jedes Element in der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Weitere Informationen finden Sie unter [Gewusst wie: Anzeigen nicht gebundener Steuerelemente in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md).  
  
 Sie können auch Binden an eine Datenquelle zur Laufzeit durch Festlegen der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A>-Eigenschaft `True` und Zuweisen von einer Datenquelle, die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A>Eigenschaft.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DataSource%2A> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.VirtualMode%2A> In diesem Fall müssen Sie alle Interaktionen mit der Datenquelle verwalten. Weitere Informationen finden Sie unter [Virtueller Modus im DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/virtual-mode-in-the-datarepeater-control-visual-studio.md).  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-data-bound-datarepeater"></a>Erstellen von datengebundenen DataRepeater  
  
1.  Ziehen Sie ein <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>-Steuerelement aus der **Visual Basic PowerPacks** Registerkarte der **Toolbox** in ein Formular oder Containersteuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
2.  Größe der Größe und Position Ziehpunkte, und platzieren Sie das Steuerelement.  
  
     Beachten Sie, dass das Steuerelement über zwei rechteckige Bereiche verfügt. Der obere Bereich ist die *Elementvorlage*; die Vorlage hinzugefügten Steuerelemente werden in jedem Element wiederholt die <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement zur Laufzeit.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> Der untere Bereich ist der *Viewport*, wo die Elemente angezeigt werden soll.  
  
     Sie können auch die Größe und position des Steuerelements oder der Elementvorlage durch Ändern der **Größe** und **Position** Eigenschaften im Eigenschaftenfenster angezeigt.  
  
3.  Klicken Sie im Menü **Daten** auf **Datenquellen anzeigen**.  
  
    > [!NOTE]
    >  Wenn die **Datenquellen** Fenster leer ist, fügen Sie eine Datenquelle hinzu. Weitere Informationen finden Sie unter [neue Datenquellen hinzufügen](https://docs.microsoft.com/visualstudio/data-tools/add-new-data-sources).  
  
4.  In der **Datenquellen** Fenster Wählen Sie den Knoten den obersten Ebene für die Tabelle, die die Daten enthält, die Sie binden möchten.  
  
5.  Ändern Sie den Ablagetyp der Tabelle `Details` durch Klicken auf `Details` in der Dropdown-Liste auf den Knoten der Tabelle.  
  
6.  Wählen Sie den Tabellenknoten, und ziehen Sie es in den Bereich der Item-Vorlage von der <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>Steuerelement.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
  
     Sie können angeben, welche Arten von Steuerelementen für jedes Feld angezeigt werden. Weitere Informationen finden Sie unter [legen Sie das Steuerelement beim Ziehen aus dem Datenquellenfenster erstellt werden](https://docs.microsoft.com/visualstudio/data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>   
 [Einführung in das DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)   
 [Gewusst wie: Anzeigen von nicht gebundenen Steuerelementen in einem DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)   
 [Gewusst wie: Erstellen einer Master-/Detailformulars mit zwei DataRepeater-Steuerelementen (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)   
 [Gewusst wie: Ändern der Darstellung eines DataRepeater-Steuerelements](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)   
 [Problembehandlung beim DataRepeater-Steuerelement](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
