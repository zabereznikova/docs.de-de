---
title: 'Fehler beim Erstellen des Assemblymanifests: &lt;Fehlermeldung&gt;'
ms.date: 07/20/2015
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
ms.openlocfilehash: b3ea5b502abd318c34d957bf7f540602c53c9e6b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588300"
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="26fbf-102">Fehler beim Erstellen des Assemblymanifests: &lt;Fehlermeldung&gt;</span><span class="sxs-lookup"><span data-stu-id="26fbf-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="26fbf-103">Visual Basic-Compiler Ruft den Assemblylinker (Al.exe, auch bekannt als Alink) auf, um eine Assembly mit einem Manifest zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="26fbf-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="26fbf-104">Der Linker meldet einen Fehler in der Vorausgabestufe der Assemblyerstellung.</span><span class="sxs-lookup"><span data-stu-id="26fbf-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="26fbf-105">Zu diesem Fehler kann es kommen, wenn es Probleme mit der angegebenen Schlüsseldatei oder dem angegebenen Schlüsselcontainer gibt.</span><span class="sxs-lookup"><span data-stu-id="26fbf-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="26fbf-106">Um eine Assembly vollständig zu signieren, müssen Sie eine gültige Schlüsseldatei bereitstellen, die Informationen zu den öffentlichen und privaten Schlüsseln enthält.</span><span class="sxs-lookup"><span data-stu-id="26fbf-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="26fbf-107">Um das Signieren einer Assembly zu verzögern, müssen Sie das Kontrollkästchen **Nur verzögerte Signierung** aktivieren und eine gültige Schlüsseldatei angeben, die Informationen zum öffentlichen Schlüssel enthält.</span><span class="sxs-lookup"><span data-stu-id="26fbf-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="26fbf-108">Der private Schlüssel ist nicht erforderlich, wenn eine Assembly verzögert signiert wird.</span><span class="sxs-lookup"><span data-stu-id="26fbf-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="26fbf-109">Weitere Informationen finden Sie unter [Vorgehensweise: Signieren einer Assembly mit einem starken Namen](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span><span class="sxs-lookup"><span data-stu-id="26fbf-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
 <span data-ttu-id="26fbf-110">**Fehler-ID:** BC30140</span><span class="sxs-lookup"><span data-stu-id="26fbf-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="26fbf-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="26fbf-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="26fbf-112">Überprüfen Sie die angegebene Fehlermeldung, und wenden Sie sich an das Thema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="26fbf-112">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="26fbf-113">für Fehler AL1019 Weitere erläuterungen und Hinweise zu erhalten</span><span class="sxs-lookup"><span data-stu-id="26fbf-113">for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="26fbf-114">Wenn der Fehler weiterhin besteht, tragen Sie Informationen zu den Umständen zusammen, und benachrichtigen Sie den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="26fbf-114">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26fbf-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26fbf-115">See Also</span></span>  
 [<span data-ttu-id="26fbf-116">Vorgehensweise: Signieren einer Assembly mit einem starken Namen</span><span class="sxs-lookup"><span data-stu-id="26fbf-116">How to: Sign an Assembly with a Strong Name</span></span>](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="26fbf-117">Seite „Signierung“, Projekt-Designer</span><span class="sxs-lookup"><span data-stu-id="26fbf-117">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)  
 <span data-ttu-id="26fbf-118">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span><span class="sxs-lookup"><span data-stu-id="26fbf-118">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span>  
 [<span data-ttu-id="26fbf-119">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="26fbf-119">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
