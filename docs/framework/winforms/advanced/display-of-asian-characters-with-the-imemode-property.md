---
title: Anzeigen asiatischer Zeichen mit der ImeMode-Eigenschaft
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4ba86b0c1343d84e65f0e3f9ff48a09b3a80a27a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a>Anzeigen asiatischer Zeichen mit der ImeMode-Eigenschaft
Die <xref:System.Windows.Forms.Control.ImeMode%2A> Eigenschaft wird in Formularen und Steuerelementen verwendet, um einen bestimmten Modus für einen Eingabemethoden-Editor (IME) zu erzwingen. Der IME ist eine wichtige Komponente beim Schreiben von chinesischen, japanischen und koreanischen Skripts, da diese Schriftsysteme mehr Zeichen enthalten als für eine normale Tastatur codiert werden können. Beispiel: In ein bestimmtes Textfeld sollen nur ASCII-Zeichen eingetragen werden dürfen. In diesem Fall können Sie festlegen der <xref:System.Windows.Forms.Control.ImeMode%2A> Eigenschaft <xref:System.Windows.Forms.ImeMode> und Benutzer werden nur ASCII-Zeichen für dieses bestimmte Textfeld eingeben. Der Standardwert der <xref:System.Windows.Forms.Control.ImeMode%2A> Eigenschaft <xref:System.Windows.Forms.ImeMode>, sodass, wenn Sie die Eigenschaft für ein Formular festlegen, alle Steuerelemente des Formulars diese Einstellung erben. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.Control.ImeMode%2A> ) und <xref:System.Windows.Forms.ImeMode>.  
  
## <a name="see-also"></a>Siehe auch  
 [Globalisieren von Windows Forms](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)
