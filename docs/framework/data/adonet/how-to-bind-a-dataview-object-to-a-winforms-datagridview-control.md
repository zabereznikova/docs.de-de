---
title: 'Vorgehensweise: Binden eines DataView-Objekts an ein Windows Forms-DataGridView-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: 7035c96208f6cad1f606727894e9d05aa51024a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033929"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a>Vorgehensweise: Binden eines DataView-Objekts an ein Windows Forms-DataGridView-Steuerelement
Das <xref:System.Windows.Forms.DataGridView>-Steuerelement ermöglicht die flexible Anzeige von Daten in tabellarischer Form. Das <xref:System.Windows.Forms.DataGridView> unterstützt das Standard-Datenbindungsmodell von Windows Forms und ermöglicht so die Bindung an eine <xref:System.Data.DataView> und eine Vielzahl anderer Datenquellen. In den meisten Fällen dürfte jedoch eine Bindung an eine <xref:System.Windows.Forms.BindingSource>-Komponente erfolgen, die sich um die Details der Interaktion mit der Datenquelle kümmert.  
  
 Weitere Informationen zu den <xref:System.Windows.Forms.DataGridView> steuern, finden Sie unter [Übersicht über das DataGridView-Steuerelement](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a>So verbinden Sie ein "DataGridView"-Steuerelement mit einer "DataView"  
  
1. Implementieren Sie eine Methode, mit der die Details des Abrufens von Daten aus einer Datenbank behandelt werden. Das folgende Codebeispiel implementiert eine `GetData`-Methode, die eine <xref:System.Data.SqlClient.SqlDataAdapter>-Komponente initialisiert, und verwendet diese, um ein <xref:System.Data.DataSet> aufzufüllen. Sorgen Sie dafür, dass die `connectionString`-Variable auf einen Wert gesetzt wird, der für Ihre Datenbank geeignet ist. Sie benötigen Zugriff auf einen Server, auf dem die SQL Server-AdventureWorks-Beispieldatenbank installiert ist.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2. Binden Sie im <xref:System.Windows.Forms.Form.Load>-Ereignishandler Ihres Formulars das <xref:System.Windows.Forms.DataGridView>-Steuerelement an die <xref:System.Windows.Forms.BindingSource>-Komponente, und verwenden Sie die `GetData`-Methode, um Daten aus der Datenbank abzurufen. Die <xref:System.Data.DataView> wird über die Contact[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-<xref:System.Data.DataTable> aus einer <xref:System.Windows.Forms.BindingSource>-Abfrage erstellt und dann an die -Komponente gebunden.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a>Siehe auch

- [Datenbindung und LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
