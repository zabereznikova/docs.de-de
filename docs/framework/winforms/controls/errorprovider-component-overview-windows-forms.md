---
title: "Übersicht über die ErrorProvider-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ErrorProvider
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error messages [Windows Forms], displaying
- ErrorProvider component [Windows Forms], about ErrorProvider component
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 589735156ad4d6d639c2449d6bd693e2b3a32d50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="errorprovider-component-overview-windows-forms"></a><span data-ttu-id="b5840-102">Übersicht über die ErrorProvider-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b5840-102">ErrorProvider Component Overview (Windows Forms)</span></span>
<span data-ttu-id="b5840-103">Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) Komponente dient zum Überprüfen von Benutzereingaben in einem Formular oder Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b5840-103">The Windows Forms [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) component is used to validate user input on a form or control.</span></span> <span data-ttu-id="b5840-104">Es wird in der Regel in Verbindung mit Validieren von Benutzereingaben in einem Formular oder die Anzeige von Fehlern innerhalb eines Datasets verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5840-104">It is typically used in conjunction with validating user input on a form, or displaying errors within a dataset.</span></span> <span data-ttu-id="b5840-105">Ein ErrorProvider-Symbol ist eine bessere Alternative als eine Fehlermeldung in einem Meldungsfeld angezeigt, da sobald ein Meldungsfeld geschlossen wird, die Fehlermeldung nicht mehr sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="b5840-105">An error provider is a better alternative than displaying an error message in a message box, because once a message box is dismissed, the error message is no longer visible.</span></span> <span data-ttu-id="b5840-106">Die <xref:System.Windows.Forms.ErrorProvider> Komponente zeigt ein Fehlersymbol (![Symbol "ErrorProvider"](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "VbErrorProviderIcon")) neben dem betreffenden Steuerelement, z. B. ein Textfeld; Wenn der Benutzer den Mauszeiger über positioniert das Symbol für Zertifikatfehler, wird eine QuickInfo, die Zeichenfolge der Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5840-106">The <xref:System.Windows.Forms.ErrorProvider> component displays an error icon (![ErrorProvider icon](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.gif "vbErrorProviderIcon")) next to the relevant control, such as a text box; when the user positions the mouse pointer over the error icon, a ToolTip appears, showing the error message string.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="b5840-107">Wichtige Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b5840-107">Key Properties</span></span>  
 <span data-ttu-id="b5840-108">Die <xref:System.Windows.Forms.ErrorProvider> sind wichtige Komponenteneigenschaften <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, und <xref:System.Windows.Forms.ErrorProvider.Icon%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5840-108">The <xref:System.Windows.Forms.ErrorProvider> component's key properties are <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A>, and <xref:System.Windows.Forms.ErrorProvider.Icon%2A>.</span></span> <span data-ttu-id="b5840-109">Bei Verwendung <xref:System.Windows.Forms.ErrorProvider> Komponente mit dem von datengebundenen Steuerelementen, die <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> Eigenschaft muss auf den entsprechenden Container (in der Regel das Windows Form) festgelegt werden, in der Reihenfolge für die Komponente auf dem Formular ein Fehlersymbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5840-109">When using <xref:System.Windows.Forms.ErrorProvider> component with data-bound controls, the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property must be set to the appropriate container (usually the Windows Form) in order for the component to display an error icon on the form.</span></span> <span data-ttu-id="b5840-110">Wenn die Komponente im Designer hinzugefügt wird die <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> Eigenschaft das zugehörige Formular festgelegt wird; Wenn Sie das Steuerelement im Code hinzufügen, müssen Sie es selbst festlegen.</span><span class="sxs-lookup"><span data-stu-id="b5840-110">When the component is added in the designer, the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property is set to the containing form; if you add the control in code, you must set it yourself.</span></span>  
  
 <span data-ttu-id="b5840-111">Die <xref:System.Windows.Forms.ErrorProvider.Icon%2A> Eigenschaft kann auf ein benutzerdefiniertes Fehlersymbol anstelle des standardmäßigen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b5840-111">The <xref:System.Windows.Forms.ErrorProvider.Icon%2A> property can be set to a custom error icon instead of the default.</span></span> <span data-ttu-id="b5840-112">Wenn die <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> Eigenschaft festgelegt ist, die <xref:System.Windows.Forms.ErrorProvider> Komponente kann Fehlermeldungen für ein Dataset angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b5840-112">When the <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> property is set, the <xref:System.Windows.Forms.ErrorProvider> component can display error messages for a dataset.</span></span> <span data-ttu-id="b5840-113">Die wichtigste Methode der der <xref:System.Windows.Forms.ErrorProvider> Komponente ist die <xref:System.Windows.Forms.ErrorProvider.SetError%2A> -Methode, die angibt, dass die Zeichenfolge der Fehlermeldung und, in dem das Symbol "Fehler" angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b5840-113">The key method of the <xref:System.Windows.Forms.ErrorProvider> component is the <xref:System.Windows.Forms.ErrorProvider.SetError%2A> method, which specifies the error message string and where the error icon should appear.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b5840-114">Die <xref:System.Windows.Forms.ErrorProvider> Komponente leistet keine integrierten Unterstützung für Eingabehilfen-Clients.</span><span class="sxs-lookup"><span data-stu-id="b5840-114">The <xref:System.Windows.Forms.ErrorProvider> component does not provide built-in support for accessibility clients.</span></span> <span data-ttu-id="b5840-115">Um die Anwendung zugreifen können, wenn diese Komponente verwenden, müssen Sie einen zusätzliche zugänglichen Feedbackmechanismus bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b5840-115">To make your application accessible when using this component, you must provide an additional, accessible feedback mechanism.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5840-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5840-116">See Also</span></span>  
 <xref:System.Windows.Forms.ErrorProvider>  
 [<span data-ttu-id="b5840-117">Gewusst wie: Anzeigen von Fehlern innerhalb eines Datasets mit der ErrorProvider-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b5840-117">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)  
 [<span data-ttu-id="b5840-118">Gewusst wie: Anzeigen von Fehlersymbolen für die Formularvalidierung mit der ErrorProvider-Komponente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b5840-118">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
