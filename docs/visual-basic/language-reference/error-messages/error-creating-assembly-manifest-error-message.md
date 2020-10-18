---
title: 'Fehler beim Erstellen des Assemblymanifests: <error message>'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: a772167966c4ec858197cc2032f4ae3d4e86070c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163414"
---
# <a name="bc30140-error-creating-assembly-manifest-error-message"></a><span data-ttu-id="872f4-102">BC30140: Fehler beim Erstellen des Assemblymanifests: \<error message></span><span class="sxs-lookup"><span data-stu-id="872f4-102">BC30140: Error creating assembly manifest: \<error message></span></span>

<span data-ttu-id="872f4-103">Der Visual Basic-Compiler ruft den Assemblylinker (Al.exe, auch bekannt als ALink) auf, um eine Assembly mit einem Manifest zu generieren.</span><span class="sxs-lookup"><span data-stu-id="872f4-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="872f4-104">Der Linker meldet einen Fehler in der Vorausgabestufe der Assemblyerstellung.</span><span class="sxs-lookup"><span data-stu-id="872f4-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>

 <span data-ttu-id="872f4-105">Zu diesem Fehler kann es kommen, wenn es Probleme mit der angegebenen Schlüsseldatei oder dem angegebenen Schlüsselcontainer gibt.</span><span class="sxs-lookup"><span data-stu-id="872f4-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="872f4-106">Um eine Assembly vollständig zu signieren, müssen Sie eine gültige Schlüsseldatei bereitstellen, die Informationen zu den öffentlichen und privaten Schlüsseln enthält.</span><span class="sxs-lookup"><span data-stu-id="872f4-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="872f4-107">Um das Signieren einer Assembly zu verzögern, müssen Sie das Kontrollkästchen **Nur verzögerte Signierung** aktivieren und eine gültige Schlüsseldatei angeben, die Informationen zum öffentlichen Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="872f4-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="872f4-108">Der private Schlüssel ist nicht erforderlich, wenn eine Assembly verzögert signiert wird.</span><span class="sxs-lookup"><span data-stu-id="872f4-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="872f4-109">Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../standard/assembly/sign-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="872f4-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../standard/assembly/sign-strong-name.md).</span></span>

 <span data-ttu-id="872f4-110">**Fehler-ID:** BC30140</span><span class="sxs-lookup"><span data-stu-id="872f4-110">**Error ID:** BC30140</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="872f4-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="872f4-111">To correct this error</span></span>

1. <span data-ttu-id="872f4-112">Überprüfen Sie die Fehlermeldung in Anführungszeichen, und lesen Sie das Thema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)</span><span class="sxs-lookup"><span data-stu-id="872f4-112">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="872f4-113">Fehler AL1019 weitere Erläuterung und Ratschläge</span><span class="sxs-lookup"><span data-stu-id="872f4-113">for error AL1019 further explanation and advice</span></span>

2. <span data-ttu-id="872f4-114">Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="872f4-114">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="872f4-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="872f4-115">See also</span></span>

- [<span data-ttu-id="872f4-116">How to: Signieren einer Assembly mit einem starken Namen</span><span class="sxs-lookup"><span data-stu-id="872f4-116">How to: Sign an Assembly with a Strong Name</span></span>](../../../standard/assembly/sign-strong-name.md)
- [<span data-ttu-id="872f4-117">Seite "Signierung", Projekt-Designer</span><span class="sxs-lookup"><span data-stu-id="872f4-117">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)
- [<span data-ttu-id="872f4-118">Al.exe</span><span class="sxs-lookup"><span data-stu-id="872f4-118">Al.exe</span></span>](../../../framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="872f4-119">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="872f4-119">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
