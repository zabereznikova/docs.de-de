---
title: 'Gewusst wie: Verwenden von Sonderzeichen in XAML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79df87d716224cb8681c1688d94fe56077452c1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="8fe37-102">Gewusst wie: Verwenden von Sonderzeichen in XAML</span><span class="sxs-lookup"><span data-stu-id="8fe37-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="8fe37-103">Markupdateien, die in erstellt werden [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] werden automatisch gespeichert, der [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8-Dateiformat, was bedeutet, dass die meisten Sonderzeichen wie z. B. Akzente, richtig codiert sind.</span><span class="sxs-lookup"><span data-stu-id="8fe37-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="8fe37-104">Es gibt jedoch eine Reihe von häufig verwendeten Sonderzeichen, die anders behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="8fe37-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="8fe37-105">Führen Sie die folgende Sonderzeichen enthalten die [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard zum Codieren.</span><span class="sxs-lookup"><span data-stu-id="8fe37-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)][!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="8fe37-106">Die folgende Tabelle zeigt die Syntax zum Codieren dieser Sonderzeichen:</span><span class="sxs-lookup"><span data-stu-id="8fe37-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="8fe37-107">Zeichen</span><span class="sxs-lookup"><span data-stu-id="8fe37-107">Character</span></span>|<span data-ttu-id="8fe37-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="8fe37-108">Syntax</span></span>|<span data-ttu-id="8fe37-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fe37-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`<`|<span data-ttu-id="8fe37-110">Kleiner als-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8fe37-110">Less than symbol.</span></span>|  
|>|`>`|<span data-ttu-id="8fe37-111">Größer als-Zeichen</span><span class="sxs-lookup"><span data-stu-id="8fe37-111">Greater than sign.</span></span>|  
|&|`&`|<span data-ttu-id="8fe37-112">Und-Zeichen (&)</span><span class="sxs-lookup"><span data-stu-id="8fe37-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="8fe37-113">"</span><span class="sxs-lookup"><span data-stu-id="8fe37-113">"</span></span>|`"`|<span data-ttu-id="8fe37-114">Doppeltes Anführungszeichen</span><span class="sxs-lookup"><span data-stu-id="8fe37-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="8fe37-115">Wenn Erstellung einer Markupdatei mit einem Text-Editor, z. B. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Editor, müssen Sie die Datei im Speichern der [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] Dateiformat um beizubehalten UTF-8 codiert Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8fe37-115">If you create a markup file using a text editor, such as [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="8fe37-116">Das folgende Beispiel zeigt, wie Sie Sonderzeichen im Text beim Erstellen von Markup verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8fe37-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fe37-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8fe37-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
