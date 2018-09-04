---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d093b8ce4413a375e79eec239be37e83ac674d05
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509672"
---
# <a name="-errorreport"></a><span data-ttu-id="cc862-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="cc862-102">-errorreport</span></span>

<span data-ttu-id="cc862-103">Gibt an, wie interne Compilerfehler von der Visual Basic-Compiler gemeldet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cc862-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="cc862-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc862-104">Syntax</span></span>

```
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="cc862-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc862-105">Remarks</span></span>

<span data-ttu-id="cc862-106">Diese Option bietet eine komfortable Möglichkeit, einen interner Compilerfehler (ICE) von Visual Basic, Visual Basic-Team bei Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc862-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="cc862-107">Standardmäßig sendet der Compiler keine Informationen an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc862-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="cc862-108">Allerdings kann diese Option Wenn einen interner Compilerfehler auftritt, Sie den Fehler an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="cc862-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="cc862-109">Diese Informationen helfen Microsoft-Techniker, die die Ursache zu identifizieren und die nächste Version von Visual Basic zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="cc862-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="cc862-110">Die Fähigkeit eines Benutzers zum Senden von Berichten hängt von Berechtigungen für Richtlinien für Computer und Benutzer.</span><span class="sxs-lookup"><span data-stu-id="cc862-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="cc862-111">Der folgenden Tabelle werden die Auswirkungen der `-errorreport` Option.</span><span class="sxs-lookup"><span data-stu-id="cc862-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="cc862-112">Option</span><span class="sxs-lookup"><span data-stu-id="cc862-112">Option</span></span>|<span data-ttu-id="cc862-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="cc862-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="cc862-114">Wenn ein interner Compilerfehler auftritt, wird ein Dialogfeld erscheint, so dass Sie die genauen Daten anzeigen können, die der Compiler erfasst.</span><span class="sxs-lookup"><span data-stu-id="cc862-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="cc862-115">Sie können ermitteln, ob keine vertraulichen Informationen in den Fehlerbericht und treffen einer Entscheidung, ob sie sich an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="cc862-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="cc862-116">Wenn Sie sie senden möchten, und die Richtlinieneinstellungen für Computer- und zulassen, sendet der Compiler die Daten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc862-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="cc862-117">Der Fehlerbericht wird in die Warteschlange gesetzt.</span><span class="sxs-lookup"><span data-stu-id="cc862-117">Queues the error report.</span></span> <span data-ttu-id="cc862-118">Wenn Sie sich mit Administratorberechtigungen anmelden, können Sie Fehler melden, seit dem letzten mit dem Sie angemeldet wurden (Sie werden nicht aufgefordert, Fehlerberichte mehr als einmal alle drei Tage zu senden).</span><span class="sxs-lookup"><span data-stu-id="cc862-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="cc862-119">Dies ist das Standardverhalten bei der `-errorreport` Option nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="cc862-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="cc862-120">Wenn ein interner Compilerfehler auftritt, und die Richtlinieneinstellungen für Computer- und zulassen, sendet der Compiler die Daten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cc862-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="cc862-121">Die Option `-errorreport:send` versucht, automatisch die Fehlerinformationen an Microsoft senden, wenn berichterstellung, indem aktiviert ist die [Windows-Fehlerberichterstattung](/windows/desktop/wer/windows-error-reporting) Systemeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="cc862-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="cc862-122">Wenn ein interner Compilerfehler auftritt, wird es nicht gesammelt oder an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="cc862-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="cc862-123">Der Compiler sendet die Daten, die in der Regel einige Quellcode enthält zum Zeitpunkt des Fehlers, der den Stapel enthält.</span><span class="sxs-lookup"><span data-stu-id="cc862-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="cc862-124">Wenn `-errorreport` wird zusammen mit den [- Bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, und klicken Sie dann die gesamte Quelldatei gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="cc862-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="cc862-125">Diese Option wird am besten verwendet, mit der [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, da Microsoft-Techniker so leicht den Fehler reproduzieren können.</span><span class="sxs-lookup"><span data-stu-id="cc862-125">This option is best used with the [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="cc862-126">Die `-errorreport` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="cc862-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="cc862-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc862-127">Example</span></span>

<span data-ttu-id="cc862-128">Der folgende Code versucht, kompilieren Sie `T2.vb`, und wenn der Compiler einen interner Compilerfehler auftritt, sie werden aufgefordert, den Fehlerbericht an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="cc862-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="cc862-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc862-129">See also</span></span>

- [<span data-ttu-id="cc862-130">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="cc862-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="cc862-131">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="cc862-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="cc862-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="cc862-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
