---
title: 'Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
ms.openlocfilehash: 42290fa7d9d38a57e17984ae5f1a9505b099ce1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698283"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a>Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ
Beim Erstellen von Steuerelementen, die mit Daten interagieren, ist es manchmal erforderlich, ein Steuerelement an einen Typ statt an ein Objekt zu binden. Diese Situation tritt vor allem zur Entwurfszeit auf, wenn Daten möglicherweise nicht verfügbar sind, aber die datengebundenen Steuerelemente dennoch Informationen von der öffentlichen Schnittstelle eines Typs anzeigen müssen. Sie können beispielsweise ein <xref:System.Windows.Forms.DataGridView>-Steuerelement an ein von einem Webdienst bereitgestelltes Objekt binden, und dafür sorgen, dass das <xref:System.Windows.Forms.DataGridView>-Steuerelement zur Entwurfszeit die zugehörigen Spalten mit den Membernamen eines benutzerdefinierten Typs beschriftet.  
  
 Mit der <xref:System.Windows.Forms.BindingSource>-Komponente können Sie ein Steuerelement problemlos an einen Typ binden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mithilfe einer <xref:System.Windows.Forms.BindingSource>-Komponente an einen benutzerdefinierten Typ gebunden wird. Beim Ausführen des Beispiels werden Sie feststellen, dass <xref:System.Windows.Forms.DataGridView> die Spalten, die die Eigenschaften eines `Customer`-Objekts darstellen, beschriftet hat, bevor das Steuerelement mit Daten gefüllt wird. In dem Beispiel ist eine Schaltfläche "Add Customer" enthalten, mit der dem <xref:System.Windows.Forms.DataGridView>-Steuerelement Daten hinzugefügt werden können. Wenn Sie auf die Schaltfläche klicken, wird <xref:System.Windows.Forms.BindingSource> ein neues `Customer`-Objekt hinzugefügt. In einem realen Szenario könnten die Daten durch den Aufruf eines Webdiensts oder einer anderen Datenquelle abgerufen werden.  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Kompilieren und Ausführen einer vollständigen Windows Forms-Codebeispiels mit Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [BindingSource-Komponente](../../../../docs/framework/winforms/controls/bindingsource-component.md)
