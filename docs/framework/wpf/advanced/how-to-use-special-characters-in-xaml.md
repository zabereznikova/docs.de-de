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
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="fbb88-102">Gewusst wie: Verwenden von Sonderzeichen in XAML</span><span class="sxs-lookup"><span data-stu-id="fbb88-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="fbb88-103">Markup Dateien, die in Visual Studio erstellt werden, werden automatisch im Unicode-UTF-8-Dateiformat gespeichert, was bedeutet, dass die meisten Sonderzeichen (z. b. Akzentzeichen) ordnungsgemäß codiert werden.</span><span class="sxs-lookup"><span data-stu-id="fbb88-103">Markup files that are created in Visual Studio are automatically saved in the Unicode UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="fbb88-104">Es gibt jedoch eine Reihe von häufig verwendeten Sonderzeichen, die anders behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="fbb88-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="fbb88-105">Diese Sonderzeichen folgen dem World Wide Web Consortium (W3C) [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Standard für die Codierung.</span><span class="sxs-lookup"><span data-stu-id="fbb88-105">These special characters follow the World Wide Web Consortium (W3C) [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="fbb88-106">Die folgende Tabelle zeigt die Syntax zum Codieren dieser Sonderzeichen:</span><span class="sxs-lookup"><span data-stu-id="fbb88-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="fbb88-107">Zeichen</span><span class="sxs-lookup"><span data-stu-id="fbb88-107">Character</span></span>|<span data-ttu-id="fbb88-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbb88-108">Syntax</span></span>|<span data-ttu-id="fbb88-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbb88-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="fbb88-110">Kleiner als-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="fbb88-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="fbb88-111">Größer als-Zeichen</span><span class="sxs-lookup"><span data-stu-id="fbb88-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="fbb88-112">Und-Zeichen (&)</span><span class="sxs-lookup"><span data-stu-id="fbb88-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="fbb88-113">"</span><span class="sxs-lookup"><span data-stu-id="fbb88-113">"</span></span>|`&quot;`|<span data-ttu-id="fbb88-114">Doppeltes Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="fbb88-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="fbb88-115">Wenn Sie eine Markup Datei mit einem Text-Editor erstellen, z. b. Windows Notepad, müssen Sie die Datei im Unicode-UTF-8-Dateiformat speichern, um alle codierten Sonderzeichen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="fbb88-115">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the Unicode UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="fbb88-116">Das folgende Beispiel zeigt, wie Sie Sonderzeichen im Text beim Erstellen von Markup verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fbb88-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbb88-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbb88-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
