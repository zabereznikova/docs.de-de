---
title: Übersicht über das PrintPreviewDialog-Steuerelement
ms.date: 01/08/2018
f1_keywords:
- PrintPreviewDialog
helpviewer_keywords:
- PrintPreviewDialog control (using designer), about PrintPreviewDialog
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
ms.openlocfilehash: 6fb971493336cda1e04c720dd09147e650918c3a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741408"
---
# <a name="printpreviewdialog-control-overview-windows-forms"></a><span data-ttu-id="3225b-102">Übersicht über das PrintPreviewDialog-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="3225b-102">PrintPreviewDialog control overview (Windows Forms)</span></span>

<span data-ttu-id="3225b-103">Das Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement ist ein vorkonfiguriertes Dialogfeld, in dem angezeigt wird, wie ein [PrintDocument](printdocument-component-windows-forms.md) angezeigt wird, wenn es gedruckt wird.</span><span class="sxs-lookup"><span data-stu-id="3225b-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> control is a pre-configured dialog box used to display how a [PrintDocument](printdocument-component-windows-forms.md) will appear when printed.</span></span> <span data-ttu-id="3225b-104">Verwenden Sie es in Ihrer Windows-basierten Anwendung als einfache Lösung, anstatt ein eigenes Dialogfeld zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3225b-104">Use it within your Windows-based application as a simple solution instead of configuring your own dialog box.</span></span> <span data-ttu-id="3225b-105">Das Steuerelement enthält Schaltflächen zum Drucken, Vergrößern, Anzeigen mindestens einer Seite und Schließen des Dialogfelds.</span><span class="sxs-lookup"><span data-stu-id="3225b-105">The control contains buttons for printing, zooming in, displaying one or multiple pages, and closing the dialog box.</span></span>

## <a name="key-properties-and-methods"></a><span data-ttu-id="3225b-106">Schlüsseleigenschaften und-Methoden</span><span class="sxs-lookup"><span data-stu-id="3225b-106">Key properties and methods</span></span>

<span data-ttu-id="3225b-107">Die Schlüsseleigenschaft des Steuer Elements ist <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, wodurch das Dokument als Vorschau angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3225b-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="3225b-108">Das Dokument muss ein <xref:System.Drawing.Printing.PrintDocument> Objekt sein.</span><span class="sxs-lookup"><span data-stu-id="3225b-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="3225b-109">Um das Dialogfeld anzuzeigen, müssen Sie dessen <xref:System.Windows.Forms.Form.ShowDialog%2A>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="3225b-109">In order to display the dialog box, you must call its <xref:System.Windows.Forms.Form.ShowDialog%2A> method.</span></span> <span data-ttu-id="3225b-110">Antialiasing kann dazu führen, dass der Text glatter erscheint, aber auch die Anzeige langsamer wird. Legen Sie die <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A>-Eigenschaft auf `true`fest, um Sie zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3225b-110">Anti-aliasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> property to `true`.</span></span>

<span data-ttu-id="3225b-111">Bestimmte Eigenschaften sind über die <xref:System.Windows.Forms.PrintPreviewControl> verfügbar, die die <xref:System.Windows.Forms.PrintPreviewDialog> enthält.</span><span class="sxs-lookup"><span data-stu-id="3225b-111">Certain properties are available through the <xref:System.Windows.Forms.PrintPreviewControl> that the <xref:System.Windows.Forms.PrintPreviewDialog> contains.</span></span> <span data-ttu-id="3225b-112">(Sie müssen diese <xref:System.Windows.Forms.PrintPreviewControl> dem Formular nicht hinzufügen. Sie ist automatisch im <xref:System.Windows.Forms.PrintPreviewDialog> enthalten, wenn Sie das Dialogfeld zum Formular hinzufügen.) Beispiele für Eigenschaften, die über die <xref:System.Windows.Forms.PrintPreviewControl> verfügbar sind, sind die Eigenschaften <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> und <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>, die bestimmen, wie viele Seiten horizontal und vertikal auf dem Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3225b-112">(You do not have to add this <xref:System.Windows.Forms.PrintPreviewControl> to the form; it is automatically contained within the <xref:System.Windows.Forms.PrintPreviewDialog> when you add the dialog to your form.) Examples of properties available through the <xref:System.Windows.Forms.PrintPreviewControl> are the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties, which determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="3225b-113">Sie können auf die <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>-Eigenschaft als `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in C#Visual oder `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++zugreifen.</span><span class="sxs-lookup"><span data-stu-id="3225b-113">You can access the <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> property as `PrintPreviewDialog1.PrintPreviewControl.Columns` in Visual Basic, `printPreviewDialog1.PrintPreviewControl.Columns` in Visual C#, or `printPreviewDialog1->PrintPreviewControl->Columns` in Visual C++.</span></span>

## <a name="printpreviewdialog-performance"></a><span data-ttu-id="3225b-114">PrintPreviewDialog-Leistung</span><span class="sxs-lookup"><span data-stu-id="3225b-114">PrintPreviewDialog performance</span></span>

<span data-ttu-id="3225b-115">Unter den folgenden Bedingungen wird das <xref:System.Windows.Forms.PrintPreviewDialog>-Steuerelement sehr langsam initialisiert:</span><span class="sxs-lookup"><span data-stu-id="3225b-115">Under the following conditions, the <xref:System.Windows.Forms.PrintPreviewDialog> control initializes very slowly:</span></span>

- <span data-ttu-id="3225b-116">Ein Netzwerkdrucker wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="3225b-116">A network printer is used.</span></span>
- <span data-ttu-id="3225b-117">Die Benutzereinstellungen für diesen Drucker (z. b. Duplex Einstellungen) werden geändert.</span><span class="sxs-lookup"><span data-stu-id="3225b-117">User preferences for this printer, such as duplex settings, are modified.</span></span>

<span data-ttu-id="3225b-118">Für apps, die auf dem .NET Framework 4.5.2 ausgeführt werden, können Sie den folgenden Schlüssel zum \<appSettings-> Abschnitt der Konfigurationsdatei hinzufügen, um die Leistung der <xref:System.Windows.Forms.PrintPreviewDialog> Steuerungs Initialisierung zu verbessern:</span><span class="sxs-lookup"><span data-stu-id="3225b-118">For apps running on the .NET Framework 4.5.2, you can add the following key to the \<appSettings> section of your configuration file to improve the performance of <xref:System.Windows.Forms.PrintPreviewDialog> control initialization:</span></span>

```xml
<appSettings>
   <add key="EnablePrintPreviewOptimization" value="true" />
</appSettings>
```

<span data-ttu-id="3225b-119">Wenn der `EnablePrintPreviewOptimization` Schlüssel auf einen anderen Wert festgelegt ist, oder wenn der Schlüssel nicht vorhanden ist, wird die Optimierung nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="3225b-119">If the `EnablePrintPreviewOptimization` key is set to any other value, or if the key is not present, the optimization is not applied.</span></span>

<span data-ttu-id="3225b-120">Für apps, die unter .NET Framework 4,6 oder höheren Versionen ausgeführt werden, können Sie den folgenden Schalter dem [\<appcontexungwitchoverrides->](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) -Element im [\<Runtime->](../../configure-apps/file-schema/runtime/index.md) Abschnitt der APP-Konfigurationsdatei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="3225b-120">For apps running on the .NET Framework 4.6 or later versions, you can add the following switch to the [\<AppContextSwitchOverrides>](../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element in the [\<runtime>](../../configure-apps/file-schema/runtime/index.md) section of your app config file:</span></span>

```xml
<runtime >
   <!-- AppContextSwitchOverrides values are in the form of 'key1=true|false;key2=true|false -->
   <AppContextSwitchOverrides value = "Switch.System.Drawing.Printing.OptimizePrintPreview=true" />
</runtime >
```

<span data-ttu-id="3225b-121">Wenn der Schalter nicht vorhanden ist oder auf einen anderen Wert festgelegt ist, wird die Optimierung nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="3225b-121">If the switch is not present or if it is set to any other value, the optimization is not applied.</span></span>

<span data-ttu-id="3225b-122">Wenn Sie das <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings>-Ereignis verwenden, um Druckereinstellungen zu ändern, wird die Leistung des <xref:System.Windows.Forms.PrintPreviewDialog> Steuer Elements nicht verbessert, auch wenn ein Optimierungs Konfigurationsschalter festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3225b-122">If you use the <xref:System.Drawing.Printing.PrintDocument.QueryPageSettings> event to modify printer settings, the performance of the <xref:System.Windows.Forms.PrintPreviewDialog> control will not improve even if an optimization configuration switch is set.</span></span>

## <a name="see-also"></a><span data-ttu-id="3225b-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3225b-123">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewDialog>
- [<span data-ttu-id="3225b-124">Übersicht über das PrintPreviewControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3225b-124">PrintPreviewControl Control Overview</span></span>](printpreviewcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="3225b-125">PrintPreviewDialog-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="3225b-125">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="3225b-126">Dialogfeld-Steuerelemente und -Komponenten</span><span class="sxs-lookup"><span data-stu-id="3225b-126">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
