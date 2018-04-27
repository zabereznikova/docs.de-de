---
title: 'Gewusst wie: Sicherstellen, dass die ausgewählte Zeile in einer untergeordneten Tabelle an der richtigen Position verbleibt'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- master-details view
- row position [Windows Forms]
- parent/child view [Windows Forms]
- resetting child position
- data binding [.NET Framework], row selection
- caching [.NET Framework], child position
- child position
- master/details view [Windows Forms]
- child tables row selection
- current child position
ms.assetid: c5fa2562-43a4-46fa-a604-52d8526a87bd
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30929c6163a279bc0ea47d1262f54ec5ff75a87c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-ensure-the-selected-row-in-a-child-table-remains-at-the-correct-position"></a>Gewusst wie: Sicherstellen, dass die ausgewählte Zeile in einer untergeordneten Tabelle an der richtigen Position verbleibt
Wenn Sie mit Datenbindungen in Windows Forms arbeiten, zeigen Sie diese Daten häufig in einer so genannten hierarchischen oder Master-/Detail-Ansicht an. Diese Bezeichnung bezieht sich auf ein Datenbindungsszenario, bei dem Daten aus der gleichen Quelle in zwei Steuerelementen angezeigt werden. Wird die Auswahl in einem Steuerelement geändert, ändern sich die Daten, die im zweiten Steuerelement angezeigt werden. So enthält das erste Steuerelement möglicherweise eine Kundenliste, und im zweiten Steuerelement wird eine Liste der Bestellungen angezeigt, die der im ersten Steuerelement ausgewählte Kunde getätigt hat.  
  
 Beginnend mit .NET Framework, Version 2.0, müssen Sie beim Anzeigen von Daten in einer hierarchischen Ansicht möglicherweise zusätzliche Schritte unternehmen, um sicherzustellen, dass die aktuell in der untergeordneten Tabelle ausgewählte Zeile nicht auf die erste Zeile der Tabelle zurückgesetzt wird. Hierfür müssen Sie die Position in der untergeordneten Tabelle zwischenspeichern und zurücksetzen, nachdem die übergeordnete Tabelle geändert wurde. Normalerweise erfolgt das Zurücksetzen der untergeordneten Tabelle zum ersten Mal, wenn ein Feld in einer Zeile der übergeordneten Tabelle geändert wird.  
  
### <a name="to-cache-the-current-child-position"></a>So speichern Sie die aktuelle untergeordnete Position zwischen  
  
1.  Deklarieren Sie eine ganzzahlige Variable zum Speichern der Position in der untergeordneten Liste und eine boolesche Variable, um zu speichern, ob die untergeordnete Position zwischengespeichert werden soll.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#4)]  
  
2.  Behandeln Sie das <xref:System.Windows.Forms.CurrencyManager.ListChanged>-Ereignis für den <xref:System.Windows.Forms.CurrencyManager> der Bindung, und prüfen Sie auf einen <xref:System.ComponentModel.ListChangedType> von <xref:System.ComponentModel.ListChangedType.Reset>.  
  
3.  Überprüfen Sie die aktuelle Position von <xref:System.Windows.Forms.CurrencyManager>. Ist diese größer als der erste Eintrag in der Liste (normalerweise 0), speichern Sie sie in einer Variablen.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#2)]  
  
4.  Behandeln Sie das <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged>-Ereignis für den übergeordneten Währungs-Manager der übergeordneten Liste. Legen Sie im Handler den booleschen Wert fest, um anzugeben, dass es sich nicht um ein Zwischenspeicherungsszenario handelt. Wenn <xref:System.Windows.Forms.BindingManagerBase.CurrentChanged> auftritt, handelt es sich bei der Änderung an der übergeordneten Liste um eine Positionsänderung und nicht um eine Änderung des Elementwerts.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#5)]  
  
### <a name="to-reset-the-child-position"></a>So setzen Sie die untergeordnete Position zurück  
  
1.  Behandeln Sie das <xref:System.Windows.Forms.BindingManagerBase.PositionChanged>-Ereignis für den <xref:System.Windows.Forms.CurrencyManager> der Bindung der untergeordneten Liste.  
  
2.  Setzen Sie die Position in der untergeordneten Tabelle auf die zwischengespeicherte Position zurück, die mit der vorherigen Prozedur gespeichert wurde.  
  
     [!code-csharp[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.CurrencyManagerReset#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie die aktuelle Position von <xref:System.Windows.Forms.CurrencyManager> für eine untergeordnete Tabelle gespeichert und dann zurückgesetzt wird, nachdem die Bearbeitung der übergeordneten Tabelle abgeschlossen ist. Das Beispiel enthält zwei <xref:System.Windows.Forms.DataGridView>-Steuerelemente, die mit einer <xref:System.Windows.Forms.BindingSource>-Komponente an zwei Tabellen in einem <xref:System.Data.DataSet> gebunden sind. Zwischen den beiden Tabellen wird eine Beziehung hergestellt, und diese Beziehung wird zu <xref:System.Data.DataSet> hinzugefügt. Die Position in der untergeordneten Tabelle wird zu Demonstrationszwecken anfänglich auf die dritte Zeile festgelegt.  
  
 [!code-csharp[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.CurrencyManagerReset#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.CurrencyManagerReset/VB/Form1.vb#1)]  
  
 Führen Sie die folgenden Schritte aus, um das Codebeispiel zu testen:  
  
1.  Führen Sie das Beispiel aus.  
  
2.  Vergewissern Sie sich, dass das Kontrollkästchen **Position zwischenspeichern und zurücksetzen** aktiviert ist.  
  
3.  Klicken Sie auf die Schaltfläche **Übergeordnetes Feld löschen**, um eine Änderung an einem Feld der übergeordneten Tabelle zu veranlassen. Beachten Sie, dass sich die ausgewählte Zeile in der untergeordneten Tabelle nicht ändert.  
  
4.  Schließen Sie das Beispiel, und führen Sie es erneut aus. Dies ist erforderlich, da die Rücksetzung erst nach der ersten Änderung in der übergeordneten Zeile stattfindet.  
  
5.  Deaktivieren Sie das Kontrollkästchen **Position zwischenspeichern und zurücksetzen**.  
  
6.  Klicken Sie auf die Schaltfläche **Übergeordnetes Feld löschen**. Beachten Sie, dass sich die ausgewählte Zeile in der untergeordneten Tabelle nun auf die erste Zeile ändert.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System", "System.Data", "System.Drawing", "System.Windows.Forms" und "System.XML".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Gebäude Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können dieses Beispiel auch in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] erstellen, indem Sie den Code in ein neues Projekt einfügen.  Siehe auch [Gewusst wie: Kompilieren und Ausführen eines vollständigen Windows Forms-Codebeispiels mit Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben](../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)  
 [BindingSource-Komponente](../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Datenbindung und Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
