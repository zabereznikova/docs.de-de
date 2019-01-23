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
# <a name="how-to-change-the-borders-of-windows-forms"></a><span data-ttu-id="2a7e7-102">Vorgehensweise: Ändern der Rahmen von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a7e7-102">How to: Change the Borders of Windows Forms</span></span>
<span data-ttu-id="2a7e7-103">Sie können aus mehreren Rahmenformatvorlagen auswählen, wenn Sie das Aussehen und Verhalten Ihres Windows Forms-Elements festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-103">You have several border styles to choose from when you are determining the appearance and behavior of your Windows Forms.</span></span> <span data-ttu-id="2a7e7-104">Durch Ändern der <xref:System.Windows.Forms.Form.FormBorderStyle%2A>-Eigenschaft können Sie das Verhalten des Formulars bei das Größenanpassung steuern.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-104">By changing the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property, you can control the resizing behavior of the form.</span></span> <span data-ttu-id="2a7e7-105">Zudem wirkt sich das Festlegen von <xref:System.Windows.Forms.Form.FormBorderStyle%2A> darauf aus, wie die Titelleiste angezeigt wird und mit welchen Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-105">In addition, setting the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> affects how the caption bar is displayed as well as what buttons might appear on it.</span></span> <span data-ttu-id="2a7e7-106">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.FormBorderStyle>.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-106">For more information, see <xref:System.Windows.Forms.FormBorderStyle>.</span></span>  
  
 <span data-ttu-id="2a7e7-107">Visual Studio bietet umfassende Unterstützung für diese Aufgabe.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-107">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="2a7e7-108">Weitere Information finden Sie unter [How to: Ändern der Rahmen von Windows Forms mithilfe des Designers](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="2a7e7-108">See also [How to: Change the Borders of Windows Forms Using the Designer](https://msdn.microsoft.com/library/yettzh3e\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a><span data-ttu-id="2a7e7-109">So legen Sie die Rahmenart von Windows Forms programmgesteuert fest</span><span class="sxs-lookup"><span data-stu-id="2a7e7-109">To set the border style of Windows Forms programmatically</span></span>  
  
-   <span data-ttu-id="2a7e7-110">Legen Sie die Eigenschaft <xref:System.Windows.Forms.Form.FormBorderStyle%2A> auf die gewünschte Rahmenart fest.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-110">Set the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to the style you want.</span></span> <span data-ttu-id="2a7e7-111">Im folgenden Codebeispiel wird die Rahmenart des Formulars `DlgBx1` zu <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-111">The following code example sets the border style of form `DlgBx1` to <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span></span>  
  
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
  
     <span data-ttu-id="2a7e7-112">Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Erstellen von Dialogfeldern zur Entwurfszeit](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="2a7e7-112">Also see [How to: Create Dialog Boxes at Design Time](https://msdn.microsoft.com/library/55cz5x2c\(v=vs.110\)).</span></span>  
  
     <span data-ttu-id="2a7e7-113">Darüber hinaus, wenn Sie eine Rahmenart für das Formular ausgewählt haben, die optionale **Minimieren** und **Maximieren** Schaltflächen können Sie angeben, ob eine oder beide Schaltflächen funktionsfähig sein sollen.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-113">Additionally, if you have chosen a border style for the form that provides optional **Minimize** and **Maximize** buttons, you can specify whether you want either or both of these buttons to be functional.</span></span> <span data-ttu-id="2a7e7-114">Diese Schaltflächen sind hilfreich, wenn Sie die Benutzeroberfläche genau steuern möchten.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-114">These buttons are useful when you want to closely control the user experience.</span></span> <span data-ttu-id="2a7e7-115">Die **Minimieren** und **Maximieren** Schaltflächen sind standardmäßig aktiviert, und ihre Funktionen bearbeitet wird, über die **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="2a7e7-115">The **Minimize** and **Maximize** buttons are enabled by default, and their functionality is manipulated through the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a7e7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a7e7-116">See also</span></span>
- <xref:System.Windows.Forms.FormBorderStyle>
- <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>
- [<span data-ttu-id="2a7e7-117">Erste Schritte mit Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a7e7-117">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)
