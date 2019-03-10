---
title: 'Vorgehensweise: Erstellen Sie ein Master / Detail-Formular mit zwei DataGridView-Steuerelementen in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
ms.openlocfilehash: 1a3ae14ba1dee704b3502146006bfa9f5d1ae637
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703698"
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Vorgehensweise: Erstellen Sie eine Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms
Im folgenden Codebeispiel wird ein Master-/Detailformular mit zwei <xref:System.Windows.Forms.DataGridView>-Steuerelementen erstellt, die an zwei <xref:System.Windows.Forms.BindingSource>-Komponenten gebunden sind. Die Datenquelle ist ein <xref:System.Data.DataSet>, das die Tabellen `Customers` und `Orders` aus der SQL Server-Beispieldatenbank "Northwind" sowie eine <xref:System.Data.DataRelation> enthält, mit der die beiden Tabellen über die Spalte `CustomerID` in Beziehung gesetzt werden.  
  
 Eine <xref:System.Windows.Forms.BindingSource> ist an die übergeordnete `Customers`-Tabelle im DataSet gebunden. Diese Daten werden im <xref:System.Windows.Forms.DataGridView>-Mastersteuerelement angezeigt. Die andere <xref:System.Windows.Forms.BindingSource>  ist an die erste Datenverbindung gebunden. Die <xref:System.Windows.Forms.BindingSource.DataMember%2A>-Eigenschaft der zweiten <xref:System.Windows.Forms.BindingSource> ist auf den Namen der <xref:System.Data.DataRelation> festgelegt. Dadurch zeigt das zugeordnete <xref:System.Windows.Forms.DataGridView>-Detailsteuerelement die Zeilen der untergeordneten `Orders`-Tabelle an, die der aktuellen Zeile im <xref:System.Windows.Forms.DataGridView>-Mastersteuerelement entsprechen.  
  
 Eine vollständige Erläuterung dieses Codebeispiels, finden Sie unter [Exemplarische Vorgehensweise: Erstellen eine Master-/Detailformulars mit zwei Windows Forms-DataGridView-Steuerelementen](creating-a-master-detail-form-using-two-datagridviews.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
 Verweise auf die Assemblys "System", "System.Data", "System.Windows.Forms" und "System.XML".  
  
-   Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Exemplarische Vorgehensweise: Erstellen eine Master-/Detailformulars mit zwei DataGridView-Steuerelementen in Windows Forms](creating-a-master-detail-form-using-two-datagridviews.md)
- [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md)
