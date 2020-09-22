---
title: Es wurde keine zugreifbare Main-Methode mit entsprechender Signatur in "<name>" gefunden.
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6958e778701066760aa74e3b4d566800b7527b76
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871475"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="5a73e-102">Es wurde keine zugreifbare Main-Methode mit entsprechender Signatur in "\<name>" gefunden.</span><span class="sxs-lookup"><span data-stu-id="5a73e-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>

<span data-ttu-id="5a73e-103">Für Befehlszeilen Anwendungen muss definiert sein `Sub Main` .</span><span class="sxs-lookup"><span data-stu-id="5a73e-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="5a73e-104">`Main` muss als deklariert werden `Public Shared` , als ob Sie in einer Klasse definiert ist, oder wie, `Public` Wenn Sie in einem Modul definiert ist.</span><span class="sxs-lookup"><span data-stu-id="5a73e-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="5a73e-105">**Fehler-ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="5a73e-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5a73e-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5a73e-106">To correct this error</span></span>  
  
- <span data-ttu-id="5a73e-107">Definieren `Public Sub Main` Sie eine Prozedur für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="5a73e-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="5a73e-108">Deklarieren Sie Sie nur dann als `Shared` if und only, wenn Sie Sie in einer Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="5a73e-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a73e-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a73e-109">See also</span></span>

- [<span data-ttu-id="5a73e-110">Struktur von Visual Basic-Programmen</span><span class="sxs-lookup"><span data-stu-id="5a73e-110">Structure of a Visual Basic Program</span></span>](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="5a73e-111">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="5a73e-111">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
