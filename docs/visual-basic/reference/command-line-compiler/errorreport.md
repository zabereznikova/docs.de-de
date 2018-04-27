---
title: -errorreport
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5dc321f7f927d68a9f270076640cbc6d31d2f6d5
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="-errorreport"></a><span data-ttu-id="6debf-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="6debf-102">-errorreport</span></span>
<span data-ttu-id="6debf-103">Gibt an, wie interne Compilerfehler von der Visual Basic-Compiler gemeldet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6debf-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6debf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6debf-104">Syntax</span></span>  
  
```  
-errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a><span data-ttu-id="6debf-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6debf-105">Remarks</span></span>  
 <span data-ttu-id="6debf-106">Diese Option bietet eine komfortable Möglichkeit, einen internen Compilerfehler (ICE) von Visual Basic, Visual Basic-Team bei Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6debf-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="6debf-107">Standardmäßig sendet der Compiler keine Informationen an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6debf-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="6debf-108">Jedoch, wenn einen interner Compilerfehler auftreten, mit dieser Option können Sie den Fehler an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="6debf-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="6debf-109">Diese Informationen helfen Microsoft-Experten, die die Ursache zu identifizieren und die nächste Version von Visual Basic zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="6debf-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>  
  
 <span data-ttu-id="6debf-110">Die Fähigkeit eines Benutzers zum Senden von Berichten, hängt von Computer- und Richtlinienberechtigungen ab.</span><span class="sxs-lookup"><span data-stu-id="6debf-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>  
  
 <span data-ttu-id="6debf-111">In der folgenden Tabelle werden die Auswirkungen der zusammengefasst die `-errorreport` Option.</span><span class="sxs-lookup"><span data-stu-id="6debf-111">The following table summarizes the effect of the `-errorreport` option.</span></span>  
  
|<span data-ttu-id="6debf-112">Option</span><span class="sxs-lookup"><span data-stu-id="6debf-112">Option</span></span>|<span data-ttu-id="6debf-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="6debf-113">Behavior</span></span>|  
|---|---|  
|`prompt`|<span data-ttu-id="6debf-114">Wenn ein interner Compilerfehler auftritt, wird ein Dialogfeld hochgefahren, so, dass Sie die genauen Daten anzeigen können, die der Compiler gesammelt.</span><span class="sxs-lookup"><span data-stu-id="6debf-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="6debf-115">Sie können bestimmen, ob es keine vertraulichen Informationen in den Fehlerbericht ist und treffen einer Entscheidung, ob sie sich an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="6debf-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="6debf-116">Wenn Sie sie senden möchten, und die Computer- und Benutzerrichtlinien zulassen, sendet der Compiler die Daten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6debf-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|  
|`queue`|<span data-ttu-id="6debf-117">Der Fehlerbericht wird in die Warteschlange gesetzt.</span><span class="sxs-lookup"><span data-stu-id="6debf-117">Queues the error report.</span></span> <span data-ttu-id="6debf-118">Wenn Sie sich mit Administratorrechten anmelden, können Sie Fehler melden, seit der letzten Ausführung mit dem Sie angemeldet waren (nicht werden Sie aufgefordert, Fehlerberichte Senden von mehr als einmal alle drei Tage).</span><span class="sxs-lookup"><span data-stu-id="6debf-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="6debf-119">Dies ist das Standardverhalten bei der `-errorreport` nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6debf-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|  
|`send`|<span data-ttu-id="6debf-120">Wenn ein interner Compilerfehler auftritt und die Computer- und Benutzerrichtlinien dies zulassen, sendet der Compiler die Daten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6debf-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="6debf-121">Die Option `-errorreport:send` Fehlerinformationen automatisch an Microsoft zu senden versucht.</span><span class="sxs-lookup"><span data-stu-id="6debf-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft.</span></span> <span data-ttu-id="6debf-122">Diese Option hängt von der Registrierung ab.</span><span class="sxs-lookup"><span data-stu-id="6debf-122">This option depends on the registry.</span></span> <span data-ttu-id="6debf-123">Weitere Informationen zum Festlegen der entsprechenden Werte in der Registrierung finden Sie unter [Aktivieren der automatischen Fehlerberichterstattung in Visual Studio 2008-Befehlszeilentools](http://go.microsoft.com/fwlink/?LinkID=184695).</span><span class="sxs-lookup"><span data-stu-id="6debf-123">For more information about setting the appropriate values in the registry, see [How to Turn on Automatic Error Reporting in Visual Studio 2008 Command-line Tools](http://go.microsoft.com/fwlink/?LinkID=184695).</span></span>|  
|`none`|<span data-ttu-id="6debf-124">Wenn ein interner Compilerfehler auftritt, wird er nicht erfasst oder an Microsoft übermittelt.</span><span class="sxs-lookup"><span data-stu-id="6debf-124">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|  
  
 <span data-ttu-id="6debf-125">Der Compiler sendet Daten, die in der Regel einige Quellcode enthält zum Zeitpunkt des Fehlers, der den Stapel enthält.</span><span class="sxs-lookup"><span data-stu-id="6debf-125">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="6debf-126">Wenn `-errorreport` wird verwendet, mit der [- Bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, und klicken Sie dann die gesamte Quelldatei gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="6debf-126">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>  
  
 <span data-ttu-id="6debf-127">Diese Option ist am besten verwendet, mit der [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, da Microsoft-Techniker so einfach den Fehler reproduzieren können.</span><span class="sxs-lookup"><span data-stu-id="6debf-127">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6debf-128">Die `-errorreport` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="6debf-128">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6debf-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6debf-129">Example</span></span>  
 <span data-ttu-id="6debf-130">Der folgende Code versucht, Kompilieren `T2.vb`, und wenn der Compiler einen interner Compilerfehler auftritt, sie werden aufgefordert, den Fehlerbericht an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="6debf-130">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>  
  
```  
vbc -errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6debf-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6debf-131">See Also</span></span>  
 [<span data-ttu-id="6debf-132">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="6debf-132">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="6debf-133">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="6debf-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="6debf-134">-bugreport</span><span class="sxs-lookup"><span data-stu-id="6debf-134">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
