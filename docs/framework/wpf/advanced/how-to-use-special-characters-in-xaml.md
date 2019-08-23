---
title: 'Vorgehensweise: Verwenden von Sonderzeichen in XAML'
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 61ee38319b2f0aa46690fb063f6ffe6612f993ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918433"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Vorgehensweise: Verwenden von Sonderzeichen in XAML
Markup Dateien, die in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] erstellt werden, werden automatisch [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] im UTF-8-Dateiformat gespeichert, was bedeutet, dass die meisten Sonderzeichen (z. b. Akzentzeichen) ordnungsgemäß codiert werden. Es gibt jedoch eine Reihe von häufig verwendeten Sonderzeichen, die anders behandelt werden. Diese Sonderzeichen folgen dem [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] Standard für die [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Codierung.  
  
 Die folgende Tabelle zeigt die Syntax zum Codieren dieser Sonderzeichen:  
  
|Zeichen|Syntax|Beschreibung|  
|---------------|------------|-----------------|  
|<|`&lt;`|Kleiner als-Zeichen.|  
|>|`&gt;`|Größer als-Zeichen|  
|&|`&amp;`|Und-Zeichen (&)|  
|"|`&quot;`|Doppeltes Anführungszeichen|  
  
> [!NOTE]
> Wenn Sie mit einem Text-Editor, z. b. Windows Notepad, eine Markup Datei erstellen, müssen Sie die [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] Datei im UTF-8-Dateiformat speichern, um codierte Sonderzeichen beizubehalten.  
  
 Das folgende Beispiel zeigt, wie Sie Sonderzeichen im Text beim Erstellen von Markup verwenden können.  
  
## <a name="example"></a>Beispiel  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
