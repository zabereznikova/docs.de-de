---
title: -errorreport
ms.date: 08/14/2018
helpviewer_keywords:
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
ms.openlocfilehash: b6a1c8fce17e3e5a54366c2ff4dff4e6aa668f56
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408659"
---
# <a name="-errorreport"></a><span data-ttu-id="f4a22-102">-errorreport</span><span class="sxs-lookup"><span data-stu-id="f4a22-102">-errorreport</span></span>

<span data-ttu-id="f4a22-103">Gibt an, wie interne Compilerfehler vom Visual Basic-Compiler gemeldet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f4a22-103">Specifies how the Visual Basic compiler should report internal compiler errors.</span></span>

## <a name="syntax"></a><span data-ttu-id="f4a22-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f4a22-104">Syntax</span></span>

```console
-errorreport:{ prompt | queue | send | none }
```

## <a name="remarks"></a><span data-ttu-id="f4a22-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4a22-105">Remarks</span></span>

<span data-ttu-id="f4a22-106">Mit dieser Option können Sie dem Visual Basic-Team von Microsoft auf einfache Weise einen internen Visual Basic-Compilerfehler (ICE) melden.</span><span class="sxs-lookup"><span data-stu-id="f4a22-106">This option provides a convenient way to report a Visual Basic internal compiler error (ICE) to the Visual Basic team at Microsoft.</span></span> <span data-ttu-id="f4a22-107">Standardmäßig sendet der Compiler keine Informationen an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4a22-107">By default, the compiler sends no information to Microsoft.</span></span> <span data-ttu-id="f4a22-108">Tritt jedoch ein interner Compilerfehler auf, können Sie mit dieser Option den Fehler an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="f4a22-108">However, if you do encounter an internal compiler error, this option allows you to report the error to Microsoft.</span></span> <span data-ttu-id="f4a22-109">Diese Informationen helfen Microsoft-Entwicklern bei der Ursachensuche und können dazu beitragen, das nächste Visual Basic-Release zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="f4a22-109">That information will help Microsoft engineers identify the cause and may help improve the next release of Visual Basic.</span></span>

<span data-ttu-id="f4a22-110">Ob ein Benutzer Berichte senden kann, hängt vom Computer und den Berechtigungen der Benutzerrichtlinien ab.</span><span class="sxs-lookup"><span data-stu-id="f4a22-110">A user's ability to send reports depends on machine and user policy permissions.</span></span>

<span data-ttu-id="f4a22-111">In der folgenden Tabelle werden die Auswirkungen der Option `-errorreport` zusammengefasst:</span><span class="sxs-lookup"><span data-stu-id="f4a22-111">The following table summarizes the effect of the `-errorreport` option.</span></span>

|<span data-ttu-id="f4a22-112">Option</span><span class="sxs-lookup"><span data-stu-id="f4a22-112">Option</span></span>|<span data-ttu-id="f4a22-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="f4a22-113">Behavior</span></span>|
|---|---|
|`prompt`|<span data-ttu-id="f4a22-114">Bei Auftreten eines internen Compilerfehlers wird ein Dialogfeld mit den genauen Daten angezeigt, die der Compiler gesammelt hat.</span><span class="sxs-lookup"><span data-stu-id="f4a22-114">If an internal compiler error occurs, a dialog box comes up so that you can view the exact data that the compiler collected.</span></span> <span data-ttu-id="f4a22-115">Sie entscheiden, ob der Fehlerbericht vertrauliche Informationen enthält und die Informationen an Microsoft gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f4a22-115">You can determine if there is any sensitive information in the error report and make a decision on whether to send it to Microsoft.</span></span> <span data-ttu-id="f4a22-116">Wenn Sie sich dafür entscheiden, und die Einstellungen des Computers und der Benutzerrichtlinien dies zulassen, sendet der Compiler die Daten an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4a22-116">If you decide to send it, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span>|
|`queue`|<span data-ttu-id="f4a22-117">Der Fehlerbericht wird in die Warteschlange gesetzt.</span><span class="sxs-lookup"><span data-stu-id="f4a22-117">Queues the error report.</span></span> <span data-ttu-id="f4a22-118">Wenn Sie sich mit Administratorrechten anmelden, können Sie alle Fehler melden, die seit Ihrer letzten Anmeldung aufgetreten sind (Sie werden nur etwa alle drei Tage zum Senden von Fehlerberichten aufgefordert).</span><span class="sxs-lookup"><span data-stu-id="f4a22-118">When you log in with administrator privileges, you can report any failures since the last time you were logged in (you will not be prompted to send reports for failures more than once every three days).</span></span> <span data-ttu-id="f4a22-119">Dies ist das Standardverhalten, wenn die Option `-errorreport` nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="f4a22-119">This is the default behavior when the `-errorreport` option is not specified.</span></span>|
|`send`|<span data-ttu-id="f4a22-120">Bei einem internen Compilerfehler sendet der Compiler die Daten an Microsoft, wenn die Einstellungen des Computers und der Benutzerrichtlinien dies zulassen.</span><span class="sxs-lookup"><span data-stu-id="f4a22-120">If an internal compiler error occurs, and the machine and user policy settings allow it, the compiler sends the data to Microsoft.</span></span><br /><br /> <span data-ttu-id="f4a22-121">Ist die Berichterstattung in den Systemeinstellungen der [Windows-Fehlerberichterstattung](/windows/desktop/wer/windows-error-reporting) aktiviert, versucht die Option `-errorreport:send`, automatisch Fehlerinformationen an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="f4a22-121">The option `-errorreport:send` attempts to automatically send error information to Microsoft if reporting is enabled by the [Windows Error Reporting](/windows/desktop/wer/windows-error-reporting) system settings.</span></span> |
|`none`|<span data-ttu-id="f4a22-122">Interne Compilerfehler werden weder gesammelt noch an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="f4a22-122">If an internal compiler error occurs, it will not be collected or sent to Microsoft.</span></span>|

<span data-ttu-id="f4a22-123">Der Compiler sendet Daten, die den Stapel zum Zeitpunkt des Fehlers und normalerweise auch Quellcode enthalten.</span><span class="sxs-lookup"><span data-stu-id="f4a22-123">The compiler sends data that includes the stack at the time of the error, which usually includes some source code.</span></span> <span data-ttu-id="f4a22-124">Wenn Sie `-errorreport` zusammen mit der Option [-bugreport](bugreport.md) verwenden, wird die gesamte Quelldatei gesendet.</span><span class="sxs-lookup"><span data-stu-id="f4a22-124">If `-errorreport` is used with the [-bugreport](bugreport.md) option, then the entire source file is sent.</span></span>

<span data-ttu-id="f4a22-125">Verwenden Sie die Option am besten zusammen mit der Option [-bugreport](bugreport.md), da auf diese Weise Microsoft-Entwickler den Fehler leichter reproduzieren können.</span><span class="sxs-lookup"><span data-stu-id="f4a22-125">This option is best used with the [-bugreport](bugreport.md) option, because it allows Microsoft engineers to more easily reproduce the error.</span></span>

> [!NOTE]
> <span data-ttu-id="f4a22-126">Die Option `-errorreport` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="f4a22-126">The `-errorreport` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="f4a22-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f4a22-127">Example</span></span>

<span data-ttu-id="f4a22-128">Mit dem folgenden Code soll `T2.vb` kompiliert werden. Tritt ein interner Compilerfehler auf, werden Sie vom Compiler dazu aufgefordert, den Fehlerbericht an Microsoft zu senden.</span><span class="sxs-lookup"><span data-stu-id="f4a22-128">The following code attempts to compile `T2.vb`, and if the compiler encounters an internal compiler error, it prompts you to send the error report to Microsoft.</span></span>

```console
vbc -errorreport:prompt t2.vb
```

## <a name="see-also"></a><span data-ttu-id="f4a22-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4a22-129">See also</span></span>

- [<span data-ttu-id="f4a22-130">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="f4a22-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="f4a22-131">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="f4a22-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="f4a22-132">-bugreport</span><span class="sxs-lookup"><span data-stu-id="f4a22-132">-bugreport</span></span>](bugreport.md)
