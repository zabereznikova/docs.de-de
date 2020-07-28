---
title: 'Gewusst wie: Verwenden von Sonderzeichen in XAML'
description: Erfahren Sie mehr über die Syntax für das Codieren von Sonderzeichen im Unicode-UTF-8-Dateiformat in Visual Studio zur Verwendung in XAML-Dateien in Windows Presentation Foundation.
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: ac2388fd96aa26ddd99408ac9f847ce517958568
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168362"
---
# <a name="how-to-use-special-characters-in-xaml"></a>Gewusst wie: Verwenden von Sonderzeichen in XAML
Markup Dateien, die in Visual Studio erstellt werden, werden automatisch im Unicode-UTF-8-Dateiformat gespeichert, was bedeutet, dass die meisten Sonderzeichen (z. b. Akzentzeichen) ordnungsgemäß codiert werden. Es gibt jedoch eine Reihe von häufig verwendeten Sonderzeichen, die anders behandelt werden. Diese Sonderzeichen folgen dem World Wide Web Consortium (W3C) XML-Standard für die Codierung.  
  
 Die folgende Tabelle zeigt die Syntax zum Codieren dieser Sonderzeichen:  
  
|Zeichen|Syntax|BESCHREIBUNG|  
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
