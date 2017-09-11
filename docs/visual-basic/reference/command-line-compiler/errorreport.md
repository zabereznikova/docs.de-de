---
title: / errorreport | Microsoft-Dokumentation
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
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c2f9a9daf6aed6348baeb2c4de2fe5caef70f52b
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="errorreport"></a><span data-ttu-id="dcaaa-102">/errorreport</span><span class="sxs-lookup"><span data-stu-id="dcaaa-102">/errorreport</span></span>
<span data-ttu-id="dcaaa-103">Gibt an, wie interne Compilerfehler vom [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Compiler gemeldet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-103">Specifies how the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler should report internal compiler errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcaaa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dcaaa-104">Syntax</span></span>  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a><span data-ttu-id="dcaaa-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dcaaa-105">Remarks</span></span>  
 <span data-ttu-id="dcaaa-106">Diese Option bietet eine komfortable Möglichkeit, einen [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] interner Compilerfehler (ICE) auf dem [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Team bei Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-106">This option provides a convenient way to report a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] internal compiler error (ICE) to the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] team at Microsoft.</span></span> <span data-ttu-id="dcaaa-107">Standardmäßig sendet der Compiler keine Informationen an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="dcaaa-108">Wenn Sie einen internen Fehler auftreten, kann jedoch diese Option auf den Fehler an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="dcaaa-109">Diese Informationen helfen Microsoft-Technikern, die Ursache zu identifizieren und die nächste Version von zu verbessern [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="dcaaa-109">That information will help Microsoft engineers identify the cause and may help improve the next release of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
 <span data-ttu-id="dcaaa-110">Die Fähigkeit eines Benutzers zum Senden von Berichten hängt vom Computer und den Benutzerberechtigungen ab.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>  
  
 <span data-ttu-id="dcaaa-111">Die folgende Tabelle enthält die Auswirkung der `/errorreport` Option.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-111">The following table summarizes the effect of the `/errorreport` option.</span></span>  
  
|<span data-ttu-id="dcaaa-112">Option</span><span class="sxs-lookup"><span data-stu-id="dcaaa-112">Option</span></span>|<span data-ttu-id="dcaaa-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="dcaaa-113">Behavior</span></span>|  
|---|---|  
|`prompt`|<span data-ttu-id="dcaaa-114">Wenn ein interner Compilerfehler auftritt, wird ein Dialogfeld, damit Sie genauen die Daten anzeigen können, die der Compiler erfasst.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="dcaaa-115">Sie können bestimmen, ob vertrauliche Daten im Bericht und treffen einer Entscheidung, ob Sie diese an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="dcaaa-116">Wenn Sie senden möchten, und die Computer- und Benutzerrichtlinien dies zulassen, sendet der Compiler die Daten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|  
|`queue`|<span data-ttu-id="dcaaa-117">Den Bericht-Warteschlangen.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-117">Queues the error report.</span></span> <span data-ttu-id="dcaaa-118">Wenn Sie sich mit Administratorrechten anmelden, können Sie Fehler melden, seit der letzten Sie angemeldet wurden (nicht werden Sie aufgefordert, Fehlerberichte mehr als einmal alle drei Tage senden).</span><span class="sxs-lookup"><span data-stu-id="dcaaa-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="dcaaa-119">Dies ist das Standardverhalten bei der `/errorreport` nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-119">This is the default behavior when the `/errorreport` option is not specified.</span></span>|  
|`send`|<span data-ttu-id="dcaaa-120">Wenn ein interner Compilerfehler auftritt und die Computer- und Benutzerrichtlinien dies zulassen, sendet der Compiler die Daten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="dcaaa-121">Die Option `/errorReport:send` versucht, automatisch Informationen an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-121">The option `/errorReport:send` attempts to automatically send error information to Microsoft.</span></span> <span data-ttu-id="dcaaa-122">Diese Option hängt von der Registrierung ab.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-122">This option depends on the registry.</span></span> <span data-ttu-id="dcaaa-123">Weitere Informationen zum Festlegen der entsprechenden Werte in der Registrierung finden Sie unter [Aktivieren der automatischen Fehlerberichterstattung in Visual Studio 2008-Befehlszeilentools](http://go.microsoft.com/fwlink/?LinkID=184695).</span><span class="sxs-lookup"><span data-stu-id="dcaaa-123">For more information about setting the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695).</span></span>|  
|`none`|<span data-ttu-id="dcaaa-124">Wenn ein interner Compilerfehler auftritt, wird es nicht erfasst oder an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-124">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|  
  
 <span data-ttu-id="dcaaa-125">Der Compiler sendet Daten, die im Stapel zum Zeitpunkt des Fehlers, der Quellcode in der Regel enthält enthält.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-125">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="dcaaa-126">Wenn `/errorreport` wird verwendet, mit der [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) -Option wird die gesamte Quelldatei gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-126">If `/errorreport` is used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>  
  
 <span data-ttu-id="dcaaa-127">Diese Option wird am besten verwendet, mit der [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, da Microsoft-Techniker so den Fehler einfacher reproduzieren können.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-127">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcaaa-128">Die `/errorreport` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-128">The `/errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcaaa-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dcaaa-129">Example</span></span>  
 <span data-ttu-id="dcaaa-130">Der folgende Code versucht, kompilieren Sie `T2.vb`, und wenn der Compiler einen internen Fehler, sie werden aufgefordert, den Fehlerbericht an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="dcaaa-130">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="dcaaa-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcaaa-131">See Also</span></span>  
 <span data-ttu-id="dcaaa-132">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="dcaaa-132">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="dcaaa-133"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="dcaaa-133"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="dcaaa-134"> [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)</span><span class="sxs-lookup"><span data-stu-id="dcaaa-134"> [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)</span></span>
