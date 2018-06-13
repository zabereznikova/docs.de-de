---
title: Übersicht über die ColorDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 9b4fb545a2ed35a9c7bad5e28c28d3ec42870860
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526037"
---
# <a name="colordialog-component-overview-windows-forms"></a><span data-ttu-id="79dc1-102">Übersicht über die ColorDialog-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="79dc1-102">ColorDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="79dc1-103">Windows Forms <xref:System.Windows.Forms.ColorDialog> Komponente ist ein vorkonfiguriertes Dialogfeld, das den Benutzer um eine Farbe aus einer Palette auszuwählen und Hinzufügen von benutzerdefinierten Farben zu dieser Palette ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="79dc1-103">The Windows Forms <xref:System.Windows.Forms.ColorDialog> component is a pre-configured dialog box that allows the user to select a color from a palette and to add custom colors to that palette.</span></span> <span data-ttu-id="79dc1-104">Es entspricht dem Dialogfeld, das in anderen Windows-basierten Anwendungen zur Farbauswahl angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="79dc1-104">It is the same dialog box that you see in other Windows-based applications to select colors.</span></span> <span data-ttu-id="79dc1-105">Verwenden Sie es in Ihrer auf Windows basierenden Anwendung als einfache Lösung, anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="79dc1-105">Use it within your Windows-based application as a simple solution in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="79dc1-106">Klicken Sie im Dialogfeld ausgewählte Farbe wird zurückgegeben, der <xref:System.Windows.Forms.ColorDialog.Color%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="79dc1-106">The color selected in the dialog box is returned in the <xref:System.Windows.Forms.ColorDialog.Color%2A> property.</span></span> <span data-ttu-id="79dc1-107">Wenn die <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> -Eigenschaftensatz auf `false`, die Schaltfläche "Benutzerdefinierte Farben" deaktiviert, sodass der Benutzer auf die vordefinierte Farben in der Palette beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="79dc1-107">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `false`, the "Define Custom Colors" button is disabled and the user is restricted to the predefined colors in the palette.</span></span> <span data-ttu-id="79dc1-108">Wenn die <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> -Eigenschaftensatz auf `true`, der Benutzer kann nicht Dithering Farben auswählen.</span><span class="sxs-lookup"><span data-stu-id="79dc1-108">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors.</span></span> <span data-ttu-id="79dc1-109">Um das Dialogfeld anzuzeigen, rufen Sie die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="79dc1-109">To display the dialog box, you must call its <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79dc1-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79dc1-110">See Also</span></span>  
 <xref:System.Windows.Forms.ColorDialog>  
 [<span data-ttu-id="79dc1-111">ColorDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="79dc1-111">ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)  
 [<span data-ttu-id="79dc1-112">Dialogfeld-Steuerelemente und -Komponenten</span><span class="sxs-lookup"><span data-stu-id="79dc1-112">Dialog-Box Controls and Components</span></span>](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)  
 [<span data-ttu-id="79dc1-113">Gewusst wie: Ändern der Darstellung der ColorDialog-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="79dc1-113">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
