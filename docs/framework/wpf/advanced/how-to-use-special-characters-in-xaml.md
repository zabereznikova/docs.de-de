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
ms.openlocfilehash: c593ca094487e8f7016b02870026321fbcb9a7c3
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="5c4e7-102">Gewusst wie: Verwenden von Sonderzeichen in XAML</span><span class="sxs-lookup"><span data-stu-id="5c4e7-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="5c4e7-103">Markupdateien, die in erstellt werden [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] werden automatisch gespeichert, der [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8-Dateiformat, was bedeutet, dass die meisten Sonderzeichen wie z. B. Akzente, richtig codiert sind.</span><span class="sxs-lookup"><span data-stu-id="5c4e7-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="5c4e7-104">Es gibt jedoch eine Reihe von häufig verwendeten Sonderzeichen, die anders behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="5c4e7-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="5c4e7-105">Führen Sie die folgende Sonderzeichen enthalten die [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard zum Codieren.</span><span class="sxs-lookup"><span data-stu-id="5c4e7-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="5c4e7-106">Die folgende Tabelle zeigt die Syntax zum Codieren dieser Sonderzeichen:</span><span class="sxs-lookup"><span data-stu-id="5c4e7-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="5c4e7-107">Zeichen</span><span class="sxs-lookup"><span data-stu-id="5c4e7-107">Character</span></span>|<span data-ttu-id="5c4e7-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c4e7-108">Syntax</span></span>|<span data-ttu-id="5c4e7-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c4e7-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="5c4e7-110">Kleiner als-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="5c4e7-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="5c4e7-111">Größer als-Zeichen</span><span class="sxs-lookup"><span data-stu-id="5c4e7-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="5c4e7-112">Und-Zeichen (&)</span><span class="sxs-lookup"><span data-stu-id="5c4e7-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="5c4e7-113">"</span><span class="sxs-lookup"><span data-stu-id="5c4e7-113">"</span></span>|`&quot;`|<span data-ttu-id="5c4e7-114">Doppeltes Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="5c4e7-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="5c4e7-115">Wenn Erstellung einer Markupdatei mit einem Text-Editor, z. B. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Editor, müssen Sie die Datei im Speichern der [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] Dateiformat um beizubehalten UTF-8 codiert Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5c4e7-115">If you create a markup file using a text editor, such as [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="5c4e7-116">Das folgende Beispiel zeigt, wie Sie Sonderzeichen im Text beim Erstellen von Markup verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5c4e7-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c4e7-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c4e7-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
