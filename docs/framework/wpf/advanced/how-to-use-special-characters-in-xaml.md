---
title: 'Gewusst wie: Verwenden von Sonderzeichen in XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 713428adc2e1576d1b95984b492fe84c042c0a09
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919642"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Gewusst wie: Verwenden von Sonderzeichen in XAML
Markup Dateien, die in Visual Studio erstellt werden, werden automatisch im Unicode-UTF-8-Dateiformat gespeichert, was bedeutet, dass die meisten Sonderzeichen (z. b. Akzentzeichen) ordnungsgemäß codiert werden. Es gibt jedoch eine Reihe von häufig verwendeten Sonderzeichen, die anders behandelt werden. Diese Sonderzeichen folgen dem World Wide Web Consortium (W3C) [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Standard für die Codierung.  
  
 Die folgende Tabelle zeigt die Syntax zum Codieren dieser Sonderzeichen:  
  
|Zeichen|Syntax|Beschreibung|  
|---------------|------------|-----------------|  
|<|`&lt;`|Kleiner als-Zeichen.|  
|>|`&gt;`|Größer als-Zeichen|  
|&|`&amp;`|Und-Zeichen (&)|  
|"|`&quot;`|Doppeltes Anführungszeichen|  
  
> [!NOTE]
> Wenn Sie eine Markup Datei mit einem Text-Editor erstellen, z. b. Windows Notepad, müssen Sie die Datei im Unicode-UTF-8-Dateiformat speichern, um alle codierten Sonderzeichen beizubehalten.  
  
 Das folgende Beispiel zeigt, wie Sie Sonderzeichen im Text beim Erstellen von Markup verwenden können.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
