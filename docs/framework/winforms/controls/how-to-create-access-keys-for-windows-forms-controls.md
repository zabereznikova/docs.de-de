---
title: Erstellen von Zugriffs Schlüsseln für Steuerelemente
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: 7f6b0a5838cacfc1189fba819a54b3423d567ea0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731172"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a><span data-ttu-id="707d8-102">Gewusst wie: Erstellen von Zugriffs Schlüsseln für Windows Forms Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="707d8-102">How to: Create access keys for Windows Forms controls</span></span>

<span data-ttu-id="707d8-103">Eine *Zugriffstaste* ist ein unterstrichenes Zeichen im Text eines Menüs, Menü Elements oder der Bezeichnung eines Steuer Elements, z. b. einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="707d8-103">An *access key* is an underlined character in the text of a menu, menu item, or the label of a control such as a button.</span></span> <span data-ttu-id="707d8-104">Mit einer Zugriffstaste kann der Benutzer auf eine Schaltfläche klicken, indem er die Alt-Taste in Kombination mit der vordefinierten Zugriffstaste drückt.</span><span class="sxs-lookup"><span data-stu-id="707d8-104">With an access key, the user can "click" a button by pressing the Alt key in combination with the predefined access key.</span></span> <span data-ttu-id="707d8-105">Wenn z. b. eine Schaltfläche eine Prozedur zum Drucken eines Formulars ausführt und deren `Text`-Eigenschaft auf "Drucken" festgelegt ist, wird durch das Hinzufügen eines kaufmännisches und vor dem Buchstaben "p" der Buchstabe "p" im Schaltflächen Text zur Laufzeit unterstrichen.</span><span class="sxs-lookup"><span data-stu-id="707d8-105">For example, if a button runs a procedure to print a form, and therefore its `Text` property is set to "Print," adding an ampersand before the letter "P" causes the letter "P" to be underlined in the button text at run time.</span></span> <span data-ttu-id="707d8-106">Der Benutzer kann den Befehl ausführen, der der Schaltfläche zugeordnet ist, indem er alt + P drückt.</span><span class="sxs-lookup"><span data-stu-id="707d8-106">The user can run the command associated with the button by pressing Alt+P.</span></span>

<span data-ttu-id="707d8-107">Steuerelemente, die keinen Fokus erhalten können, dürfen keine Zugriffsschlüssel aufweisen.</span><span class="sxs-lookup"><span data-stu-id="707d8-107">Controls that cannot receive focus can't have access keys.</span></span>

## <a name="programmatic"></a><span data-ttu-id="707d8-108">Programmgesteuerten</span><span class="sxs-lookup"><span data-stu-id="707d8-108">Programmatic</span></span>

<span data-ttu-id="707d8-109">Legen Sie die `Text`-Eigenschaft auf eine Zeichenfolge fest, die ein kaufmännisches und-Zeichen (&) vor dem Buchstaben enthält, der als Verknüpfung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="707d8-109">Set the `Text` property to a string that includes an ampersand (&) before the letter that will be the shortcut.</span></span>

```vb
' Set the letter "P" as an access key.
Button1.Text = "&Print"
```

```csharp
// Set the letter "P" as an access key.
button1.Text = "&Print";
```

```cpp
// Set the letter "P" as an access key.
button1->Text = "&Print";
```

> [!NOTE]
> <span data-ttu-id="707d8-110">Wenn Sie ein kaufmännisches und in einer Beschriftung verwenden möchten, ohne einen Zugriffsschlüssel zu erstellen, schließen Sie zwei kaufmännische (& &) ein.</span><span class="sxs-lookup"><span data-stu-id="707d8-110">To use an ampersand in a caption without creating an access key, include two ampersands (&&).</span></span> <span data-ttu-id="707d8-111">Ein kaufmännisches und-Zeichen wird in der Beschriftung angezeigt, und es werden keine Zeichen unterstrichen.</span><span class="sxs-lookup"><span data-stu-id="707d8-111">A single ampersand is displayed in the caption and no characters are underlined.</span></span>

## <a name="designer"></a><span data-ttu-id="707d8-112">-Designer</span><span class="sxs-lookup"><span data-stu-id="707d8-112">Designer</span></span>

<span data-ttu-id="707d8-113">Legen Sie im **Eigenschaften** Fenster von Visual Studio die **Text** -Eigenschaft auf eine Zeichenfolge fest, die ein kaufmännisches und-Zeichen ("&") vor dem Buchstaben enthält, der als Zugriffstaste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="707d8-113">In the **Properties** window of Visual Studio, set the **Text** property to a string that includes an ampersand ('&') before the letter that will be the access key.</span></span> <span data-ttu-id="707d8-114">Wenn Sie z. b. den Buchstaben "P" als Zugriffsschlüssel festlegen möchten, geben Sie **& Print**ein.</span><span class="sxs-lookup"><span data-stu-id="707d8-114">For example, to set the letter "P" as the access key, enter **&Print**.</span></span>

## <a name="see-also"></a><span data-ttu-id="707d8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="707d8-115">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="707d8-116">Gewusst wie: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="707d8-116">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="707d8-117">Gewusst wie: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Texts</span><span class="sxs-lookup"><span data-stu-id="707d8-117">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="707d8-118">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="707d8-118">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
