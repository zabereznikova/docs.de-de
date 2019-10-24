---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: a9741f7a8283f8603e02dae5abea151c6ee5d75e
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775670"
---
# <a name="-errorreport"></a><span data-ttu-id="28c1c-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="28c1c-102">-errorreport</span></span>

<span data-ttu-id="28c1c-103">Gibt an, wie der Visual Basic Compiler interne Compilerfehler melden soll.</span><span class="sxs-lookup"><span data-stu-id="28c1c-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="28c1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28c1c-104">Syntax</span></span>

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="28c1c-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28c1c-105">Remarks</span></span>

<span data-ttu-id="28c1c-106">Diese Option bietet eine bequeme Möglichkeit, dem Visual Basic Team bei Microsoft eine Visual Basic interner Compilerfehler (ICE) zu melden.</span><span class="sxs-lookup"><span data-stu-id="28c1c-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="28c1c-107">Standardmäßig sendet der Compiler keine Informationen an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="28c1c-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="28c1c-108">Wenn jedoch ein interner Compilerfehler auftritt, können Sie mit dieser Option den Fehler an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="28c1c-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="28c1c-109">Diese Informationen helfen den Microsoft-Technikern dabei, die Ursache zu identifizieren und die nächste Version von Visual Basic zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="28c1c-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="28c1c-110">Die Fähigkeit eines Benutzers, Berichte zu senden, hängt von den Berechtigungen für Computer-und Benutzerrichtlinien ab.</span><span class="sxs-lookup"><span data-stu-id="28c1c-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="28c1c-111">In der folgenden Tabelle werden die Auswirkungen der Option `-errorreport` zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="28c1c-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="28c1c-112">Option</span><span class="sxs-lookup"><span data-stu-id="28c1c-112">Option</span></span>|<span data-ttu-id="28c1c-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="28c1c-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="28c1c-114">Wenn ein interner Compilerfehler auftritt, wird ein Dialogfeld angezeigt, in dem Sie die genauen Daten anzeigen können, die der Compiler gesammelt hat.</span><span class="sxs-lookup"><span data-stu-id="28c1c-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="28c1c-115">Sie können feststellen, ob vertrauliche Informationen im Fehlerbericht vorliegen, und entscheiden, ob die Informationen an Microsoft gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="28c1c-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="28c1c-116">Wenn Sie sich dafür entscheiden, Sie zu senden, und die Computer-und Benutzerrichtlinien Einstellungen dies zulassen, sendet der Compiler die Daten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="28c1c-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="28c1c-117">Der Fehlerbericht wird in die Warteschlange gesetzt.</span><span class="sxs-lookup"><span data-stu-id="28c1c-117">Queues the error report.</span></span> <span data-ttu-id="28c1c-118">Wenn Sie sich mit Administratorrechten anmelden, können Sie alle Fehler melden, die seit der letzten Anmeldung aufgetreten sind (Sie werden nicht mehr als einmal alle drei Tage aufgefordert, Berichte zu Fehlern zu senden).</span><span class="sxs-lookup"><span data-stu-id="28c1c-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="28c1c-119">Dies ist das Standardverhalten, wenn die `-errorreport`-Option nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="28c1c-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="28c1c-120">Wenn ein interner Compilerfehler auftritt und die Computer-und Benutzerrichtlinien Einstellungen dies zulassen, sendet der Compiler die Daten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="28c1c-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="28c1c-121">Die Option `-errorreport:send` versucht, automatisch Fehlerinformationen an Microsoft zu senden, wenn die Berichterstellung durch die [Windows-Fehlerberichterstattung](/windows/desktop/wer/windows-error-reporting) Systemeinstellungen aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="28c1c-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="28c1c-122">Wenn ein interner Compilerfehler auftritt, wird er nicht gesammelt oder an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="28c1c-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="28c1c-123">Der Compiler sendet Daten, die den Stapel zum Zeitpunkt des Fehlers enthalten, der normalerweise den Quellcode enthält.</span><span class="sxs-lookup"><span data-stu-id="28c1c-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="28c1c-124">Wenn `-errorreport` mit der Option [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) verwendet wird, wird die gesamte Quelldatei gesendet.</span><span class="sxs-lookup"><span data-stu-id="28c1c-124">If `-errorreport` is used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="28c1c-125">Diese Option wird am besten mit der Option [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) verwendet, da Microsoft-Technikern den Fehler einfacher reproduzieren können.</span><span class="sxs-lookup"><span data-stu-id="28c1c-125">This option is best used with the [-bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="28c1c-126">Die `-errorreport`-Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="28c1c-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="28c1c-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28c1c-127">Example</span></span>

<span data-ttu-id="28c1c-128">Der folgende Code versucht, `T2.vb` zu kompilieren. wenn der Compiler auf einen internen Compilerfehler stößt, werden Sie aufgefordert, den Fehlerbericht an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="28c1c-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="28c1c-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28c1c-129">See also</span></span>

- [<span data-ttu-id="28c1c-130">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="28c1c-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="28c1c-131">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="28c1c-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="28c1c-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="28c1c-132">-bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)
