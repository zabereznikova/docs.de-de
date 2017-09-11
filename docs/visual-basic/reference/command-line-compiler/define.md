---
title: / define (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e4eac32b4ab7259b9d3fd2ec37e21406c4cec326
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="define-visual-basic"></a><span data-ttu-id="f6b08-102">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6b08-102">/define (Visual Basic)</span></span>
<span data-ttu-id="f6b08-103">Definiert Konstanten für die bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="f6b08-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6b08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6b08-104">Syntax</span></span>  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f6b08-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f6b08-105">Arguments</span></span>  
  
|<span data-ttu-id="f6b08-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="f6b08-106">Term</span></span>|<span data-ttu-id="f6b08-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f6b08-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="f6b08-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f6b08-108">Required.</span></span> <span data-ttu-id="f6b08-109">Das zu definierende Symbol.</span><span class="sxs-lookup"><span data-stu-id="f6b08-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="f6b08-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="f6b08-110">Optional.</span></span> <span data-ttu-id="f6b08-111">Der Wert, der `symbol` zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="f6b08-111">The value to assign `symbol`.</span></span> <span data-ttu-id="f6b08-112">Wenn `value` eine Zeichenfolge ist, muss Sie von einer umgekehrten Schrägstrich und Anführungszeichen eingeschlossen sein (\\") anstelle von Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="f6b08-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="f6b08-113">Wurde kein Wert festgelegt, dann wird er als True angenommen.</span><span class="sxs-lookup"><span data-stu-id="f6b08-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6b08-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6b08-114">Remarks</span></span>  
 <span data-ttu-id="f6b08-115">Die Option `/define` hat einen ähnlichen Effekt wie das Verwenden einer `#Const`-Präprozessordirektive in der Quelldatei, außer dass mit `/define` definierte Konstanten öffentlich sind und für alle Dateien im Projekt gelten.</span><span class="sxs-lookup"><span data-stu-id="f6b08-115">The `/define` option has an effect  similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `/define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="f6b08-116">Sie können Symbole, die mit dieser Option erstellt wurden, mit der `#If`...`Then`...`#Else`-Direktive verwenden, um Quelldateien bedingt zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="f6b08-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="f6b08-117">`/d`ist die Kurzform von `/define`.</span><span class="sxs-lookup"><span data-stu-id="f6b08-117">`/d` is the short form of `/define`.</span></span>  
  
 <span data-ttu-id="f6b08-118">Sie können mehrere Symbole mit `/define` definieren, wenn Sie kommagetrennte Symboldefinitionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6b08-118">You can define multiple symbols with `/define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="f6b08-119">So definieren Sie die integrierte Visual Studio-Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="f6b08-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="f6b08-120">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f6b08-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="f6b08-121">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f6b08-121">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="f6b08-122">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="f6b08-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="f6b08-123">2.  Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="f6b08-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="f6b08-124">3.  Klicken Sie auf **erweiterte**.</span><span class="sxs-lookup"><span data-stu-id="f6b08-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="f6b08-125">4.  Ändern Sie den Wert in der **benutzerdefinierte Konstanten** Feld.</span><span class="sxs-lookup"><span data-stu-id="f6b08-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f6b08-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6b08-126">Example</span></span>  
 <span data-ttu-id="f6b08-127">Der folgende Code definiert zwei konditionelle Compilerkonstanten und verwendet sie anschließend.</span><span class="sxs-lookup"><span data-stu-id="f6b08-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 <span data-ttu-id="f6b08-128">[!code-vb[VbVbalrCompiler&#45;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f6b08-128">[!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6b08-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6b08-129">See Also</span></span>  
 <span data-ttu-id="f6b08-130">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6b08-130">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="f6b08-131"> [#If... Then... #Else-Direktive](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="f6b08-131"> [#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="f6b08-132"> [#Const-Direktive](../../../visual-basic/language-reference/directives/const-directive.md) </span><span class="sxs-lookup"><span data-stu-id="f6b08-132"> [#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) </span></span>  
<span data-ttu-id="f6b08-133"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="f6b08-133"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
