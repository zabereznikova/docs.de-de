---
title: Anzeigen asiatischer Zeichen mit der ImeMode-Eigenschaft
ms.date: 03/30/2017
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
ms.openlocfilehash: 25602e1a878443bd54411dfd6481581abebda5c7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500520"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a><span data-ttu-id="279b5-102">Anzeigen asiatischer Zeichen mit der ImeMode-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="279b5-102">Display of Asian Characters with the ImeMode Property</span></span>
<span data-ttu-id="279b5-103">Die <xref:System.Windows.Forms.Control.ImeMode%2A> Eigenschaft wird in Formularen und Steuerelementen verwendet, um einen bestimmten Modus für einen Eingabemethoden-Editor (IME) zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="279b5-103">The <xref:System.Windows.Forms.Control.ImeMode%2A> property is used by forms and controls to force a specific mode for an input method editor (IME).</span></span> <span data-ttu-id="279b5-104">Der IME ist eine wichtige Komponente beim Schreiben von chinesischen, japanischen und koreanischen Skripts, da diese Schriftsysteme mehr Zeichen enthalten als für eine normale Tastatur codiert werden können.</span><span class="sxs-lookup"><span data-stu-id="279b5-104">The IME is an essential component for writing Chinese, Japanese, and Korean scripts, since these writing systems have more characters than can be encoded for a regular keyboard.</span></span> <span data-ttu-id="279b5-105">Beispiel: In ein bestimmtes Textfeld sollen nur ASCII-Zeichen eingetragen werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="279b5-105">For example, you may want to allow only ASCII characters in a particular text box.</span></span> <span data-ttu-id="279b5-106">In diesem Fall können Sie festlegen der <xref:System.Windows.Forms.Control.ImeMode%2A> Eigenschaft <xref:System.Windows.Forms.ImeMode> und Benutzer werden nur ASCII-Zeichen für dieses Textfeld eingeben können.</span><span class="sxs-lookup"><span data-stu-id="279b5-106">In such a case you can set the <xref:System.Windows.Forms.Control.ImeMode%2A> property to <xref:System.Windows.Forms.ImeMode> and users will only be able to enter ASCII characters for that particular text box.</span></span> <span data-ttu-id="279b5-107">Der Standardwert der <xref:System.Windows.Forms.Control.ImeMode%2A> Eigenschaft <xref:System.Windows.Forms.ImeMode>, wenn Sie die Eigenschaft für ein Formular festlegen, alle Steuerelemente im Formular diese Einstellung erben.</span><span class="sxs-lookup"><span data-stu-id="279b5-107">The default value of the <xref:System.Windows.Forms.Control.ImeMode%2A> property is <xref:System.Windows.Forms.ImeMode>, so if you set the property for a form, all controls on the form will inherit that setting.</span></span> <span data-ttu-id="279b5-108">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.Control.ImeMode%2A> ) und <xref:System.Windows.Forms.ImeMode>.</span><span class="sxs-lookup"><span data-stu-id="279b5-108">For more information, see <xref:System.Windows.Forms.Control.ImeMode%2A> ) and <xref:System.Windows.Forms.ImeMode>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="279b5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="279b5-109">See also</span></span>

- [<span data-ttu-id="279b5-110">Globalisieren von Windows Forms-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="279b5-110">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
