---
title: 'Vorgehensweise: Ändern der Rahmen von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: 32e5eb60d09eca895a1fa4584c5af5a302e81ff0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558656"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a>Vorgehensweise: Ändern der Rahmen von Windows Forms
Sie können aus mehreren Rahmenformatvorlagen auswählen, wenn Sie das Aussehen und Verhalten Ihres Windows Forms-Elements festlegen möchten. Durch Ändern der <xref:System.Windows.Forms.Form.FormBorderStyle%2A>-Eigenschaft können Sie das Verhalten des Formulars bei das Größenanpassung steuern. Zudem wirkt sich das Festlegen von <xref:System.Windows.Forms.Form.FormBorderStyle%2A> darauf aus, wie die Titelleiste angezeigt wird und mit welchen Schaltflächen. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.FormBorderStyle>.  
  
 Visual Studio bietet umfassende Unterstützung für diese Aufgabe.  
  
 Weitere Information finden Sie unter [How to: Ändern der Rahmen von Windows Forms mithilfe des Designers](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a>So legen Sie die Rahmenart von Windows Forms programmgesteuert fest  
  
-   Legen Sie die Eigenschaft <xref:System.Windows.Forms.Form.FormBorderStyle%2A> auf die gewünschte Rahmenart fest. Im folgenden Codebeispiel wird die Rahmenart des Formulars `DlgBx1` zu <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Erstellen von Dialogfeldern zur Entwurfszeit](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).  
  
     Darüber hinaus, wenn Sie eine Rahmenart für das Formular ausgewählt haben, die optionale **Minimieren** und **Maximieren** Schaltflächen können Sie angeben, ob eine oder beide Schaltflächen funktionsfähig sein sollen. Diese Schaltflächen sind hilfreich, wenn Sie die Benutzeroberfläche genau steuern möchten. Die **Minimieren** und **Maximieren** Schaltflächen sind standardmäßig aktiviert, und ihre Funktionen bearbeitet wird, über die **Eigenschaften** Fenster.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.FormBorderStyle>
- <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>
- [Erste Schritte mit Windows Forms](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
