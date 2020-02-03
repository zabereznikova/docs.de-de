---
title: Binden des Steuer Elements an einen Typ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
ms.openlocfilehash: 0bc1f92ee8922990bd0e461655168f5618ba39a6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744986"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a>Gewusst wie: Binden eines Windows Forms-Steuerelements an einen Typ
Beim Erstellen von Steuerelementen, die mit Daten interagieren, ist es manchmal erforderlich, ein Steuerelement an einen Typ statt an ein Objekt zu binden. Diese Situation tritt vor allem zur Entwurfszeit auf, wenn Daten möglicherweise nicht verfügbar sind, aber die datengebundenen Steuerelemente dennoch Informationen von der öffentlichen Schnittstelle eines Typs anzeigen müssen. Sie können beispielsweise ein <xref:System.Windows.Forms.DataGridView>-Steuerelement an ein von einem Webdienst bereitgestelltes Objekt binden, und dafür sorgen, dass das <xref:System.Windows.Forms.DataGridView>-Steuerelement zur Entwurfszeit die zugehörigen Spalten mit den Membernamen eines benutzerdefinierten Typs beschriftet.  
  
 Mit der <xref:System.Windows.Forms.BindingSource>-Komponente können Sie ein Steuerelement problemlos an einen Typ binden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mithilfe einer <xref:System.Windows.Forms.BindingSource>-Komponente an einen benutzerdefinierten Typ gebunden wird. Beim Ausführen des Beispiels werden Sie feststellen, dass <xref:System.Windows.Forms.DataGridView> die Spalten, die die Eigenschaften eines `Customer`-Objekts darstellen, beschriftet hat, bevor das Steuerelement mit Daten gefüllt wird. In dem Beispiel ist eine Schaltfläche "Add Customer" enthalten, mit der dem <xref:System.Windows.Forms.DataGridView>-Steuerelement Daten hinzugefügt werden können. Wenn Sie auf die Schaltfläche klicken, wird `Customer` ein neues <xref:System.Windows.Forms.BindingSource>-Objekt hinzugefügt. In einem realen Szenario könnten die Daten durch den Aufruf eines Webdiensts oder einer anderen Datenquelle abgerufen werden.  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Verweise auf die Assemblys "System" und "System.Windows.Forms".  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [BindingSource-Komponente](bindingsource-component.md)
