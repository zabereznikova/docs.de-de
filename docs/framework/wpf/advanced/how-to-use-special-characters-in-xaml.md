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
ms.openlocfilehash: 59449637bb45f6b75462b6809c354af7972fc2e7
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740840"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="f1018-102">Gewusst wie: Verwenden von Sonderzeichen in XAML</span><span class="sxs-lookup"><span data-stu-id="f1018-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="f1018-103">Markup Dateien, die in Visual Studio erstellt werden, werden automatisch im Unicode-UTF-8-Dateiformat gespeichert, was bedeutet, dass die meisten Sonderzeichen (z. b. Akzentzeichen) ordnungsgemäß codiert werden.</span><span class="sxs-lookup"><span data-stu-id="f1018-103">Markup files that are created in Visual Studio are automatically saved in the Unicode UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="f1018-104">Es gibt jedoch eine Reihe von häufig verwendeten Sonderzeichen, die anders behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="f1018-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="f1018-105">Diese Sonderzeichen folgen dem World Wide Web Consortium (W3C) XML-Standard für die Codierung.</span><span class="sxs-lookup"><span data-stu-id="f1018-105">These special characters follow the World Wide Web Consortium (W3C) XML standard for encoding.</span></span>  
  
 <span data-ttu-id="f1018-106">Die folgende Tabelle zeigt die Syntax zum Codieren dieser Sonderzeichen:</span><span class="sxs-lookup"><span data-stu-id="f1018-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="f1018-107">Zeichen</span><span class="sxs-lookup"><span data-stu-id="f1018-107">Character</span></span>|<span data-ttu-id="f1018-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1018-108">Syntax</span></span>|<span data-ttu-id="f1018-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1018-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="f1018-110">Kleiner als-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f1018-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="f1018-111">Größer als-Zeichen</span><span class="sxs-lookup"><span data-stu-id="f1018-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="f1018-112">Und-Zeichen (&)</span><span class="sxs-lookup"><span data-stu-id="f1018-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="f1018-113">"</span><span class="sxs-lookup"><span data-stu-id="f1018-113">"</span></span>|`&quot;`|<span data-ttu-id="f1018-114">Doppeltes Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="f1018-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="f1018-115">Wenn Sie eine Markup Datei mit einem Text-Editor erstellen, z. b. Windows Notepad, müssen Sie die Datei im Unicode-UTF-8-Dateiformat speichern, um alle codierten Sonderzeichen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="f1018-115">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the Unicode UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="f1018-116">Das folgende Beispiel zeigt, wie Sie Sonderzeichen im Text beim Erstellen von Markup verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f1018-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1018-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1018-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
