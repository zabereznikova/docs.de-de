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
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="56939-103">Gewusst wie: Verwenden von Sonderzeichen in XAML</span><span class="sxs-lookup"><span data-stu-id="56939-103">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="56939-104">Markup Dateien, die in Visual Studio erstellt werden, werden automatisch im Unicode-UTF-8-Dateiformat gespeichert, was bedeutet, dass die meisten Sonderzeichen (z. b. Akzentzeichen) ordnungsgemäß codiert werden.</span><span class="sxs-lookup"><span data-stu-id="56939-104">Markup files that are created in Visual Studio are automatically saved in the Unicode UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="56939-105">Es gibt jedoch eine Reihe von häufig verwendeten Sonderzeichen, die anders behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="56939-105">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="56939-106">Diese Sonderzeichen folgen dem World Wide Web Consortium (W3C) XML-Standard für die Codierung.</span><span class="sxs-lookup"><span data-stu-id="56939-106">These special characters follow the World Wide Web Consortium (W3C) XML standard for encoding.</span></span>  
  
 <span data-ttu-id="56939-107">Die folgende Tabelle zeigt die Syntax zum Codieren dieser Sonderzeichen:</span><span class="sxs-lookup"><span data-stu-id="56939-107">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="56939-108">Zeichen</span><span class="sxs-lookup"><span data-stu-id="56939-108">Character</span></span>|<span data-ttu-id="56939-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="56939-109">Syntax</span></span>|<span data-ttu-id="56939-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="56939-110">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="56939-111">Kleiner als-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="56939-111">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="56939-112">Größer als-Zeichen</span><span class="sxs-lookup"><span data-stu-id="56939-112">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="56939-113">Und-Zeichen (&)</span><span class="sxs-lookup"><span data-stu-id="56939-113">Ampersand symbol.</span></span>|  
|<span data-ttu-id="56939-114">"</span><span class="sxs-lookup"><span data-stu-id="56939-114">"</span></span>|`&quot;`|<span data-ttu-id="56939-115">Doppeltes Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="56939-115">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="56939-116">Wenn Sie eine Markup Datei mit einem Text-Editor erstellen, z. b. Windows Notepad, müssen Sie die Datei im Unicode-UTF-8-Dateiformat speichern, um alle codierten Sonderzeichen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="56939-116">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the Unicode UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="56939-117">Das folgende Beispiel zeigt, wie Sie Sonderzeichen im Text beim Erstellen von Markup verwenden können.</span><span class="sxs-lookup"><span data-stu-id="56939-117">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56939-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56939-118">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
