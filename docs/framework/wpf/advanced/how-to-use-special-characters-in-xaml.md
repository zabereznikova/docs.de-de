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
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="db90d-102">Vorgehensweise: Verwenden von Sonderzeichen in XAML</span><span class="sxs-lookup"><span data-stu-id="db90d-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="db90d-103">Markup Dateien, die in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] erstellt werden, werden automatisch [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] im UTF-8-Dateiformat gespeichert, was bedeutet, dass die meisten Sonderzeichen (z. b. Akzentzeichen) ordnungsgemäß codiert werden.</span><span class="sxs-lookup"><span data-stu-id="db90d-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="db90d-104">Es gibt jedoch eine Reihe von häufig verwendeten Sonderzeichen, die anders behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="db90d-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="db90d-105">Diese Sonderzeichen folgen dem [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] Standard für die [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Codierung.</span><span class="sxs-lookup"><span data-stu-id="db90d-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="db90d-106">Die folgende Tabelle zeigt die Syntax zum Codieren dieser Sonderzeichen:</span><span class="sxs-lookup"><span data-stu-id="db90d-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="db90d-107">Zeichen</span><span class="sxs-lookup"><span data-stu-id="db90d-107">Character</span></span>|<span data-ttu-id="db90d-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="db90d-108">Syntax</span></span>|<span data-ttu-id="db90d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db90d-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="db90d-110">Kleiner als-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="db90d-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="db90d-111">Größer als-Zeichen</span><span class="sxs-lookup"><span data-stu-id="db90d-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="db90d-112">Und-Zeichen (&)</span><span class="sxs-lookup"><span data-stu-id="db90d-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="db90d-113">"</span><span class="sxs-lookup"><span data-stu-id="db90d-113">"</span></span>|`&quot;`|<span data-ttu-id="db90d-114">Doppeltes Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="db90d-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="db90d-115">Wenn Sie mit einem Text-Editor, z. b. Windows Notepad, eine Markup Datei erstellen, müssen Sie die [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] Datei im UTF-8-Dateiformat speichern, um codierte Sonderzeichen beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="db90d-115">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="db90d-116">Das folgende Beispiel zeigt, wie Sie Sonderzeichen im Text beim Erstellen von Markup verwenden können.</span><span class="sxs-lookup"><span data-stu-id="db90d-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db90d-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="db90d-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
