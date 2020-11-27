---
description: '#C#-Referenz: Nullable'
title: '#C#-Referenz: Nullable'
ms.date: 11/18/2020
f1_keywords:
- '#nullable'
helpviewer_keywords:
- '#nullable directive [C#]'
ms.openlocfilehash: 4c114a09f29769fcc824bcdabdc1d523e33f199d
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099446"
---
# <a name="nullable-c-reference"></a><span data-ttu-id="30ce1-103">C#-Referenz: #nullable</span><span class="sxs-lookup"><span data-stu-id="30ce1-103">#nullable (C# Reference)</span></span>

<span data-ttu-id="30ce1-104">Die Präprozessoranweisung `#nullable` legt den *Nullable-Anmerkungskontext* und den *Nullable-Warnungskontext* fest.</span><span class="sxs-lookup"><span data-stu-id="30ce1-104">The `#nullable` preprocessor directive sets the *nullable annotation context* and *nullable warning context*.</span></span> <span data-ttu-id="30ce1-105">Die Anweisung steuert, ob Nullable-Anmerkungen wirksam sind und ob Warnungen zur NULL-Zulässigkeit angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="30ce1-105">This directive controls whether nullable annotations have effect, and whether nullability warnings are given.</span></span> <span data-ttu-id="30ce1-106">Jeder Kontext ist entweder *deaktiviert* oder *aktiviert*.</span><span class="sxs-lookup"><span data-stu-id="30ce1-106">Each context is either *disabled* or *enabled*.</span></span>

<span data-ttu-id="30ce1-107">Beide Kontexte können auf Projektebene (außerhalb des C#-Quellcodes) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="30ce1-107">Both contexts can be specified at the project level (outside of C# source code).</span></span> <span data-ttu-id="30ce1-108">Die `#nullable`-Anweisung steuert die Anmerkungs- und Warnungskontexte und hat Vorrang vor anderen Einstellungen auf Projektebene.</span><span class="sxs-lookup"><span data-stu-id="30ce1-108">The `#nullable` directive controls the annotation and warning contexts and takes precedence over the project-level settings.</span></span> <span data-ttu-id="30ce1-109">Eine Anweisung legt die von ihr gesteuerten Kontexte fest, bis sie von einer anderen Anweisung überschrieben wird oder bis zum Ende der Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="30ce1-109">A directive sets the context(s) it controls until another directive overrides it, or until the end of the source file.</span></span>

<span data-ttu-id="30ce1-110">Die Auswirkungen der Anweisungen lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="30ce1-110">The effect of the directives is as follows:</span></span>

- <span data-ttu-id="30ce1-111">`#nullable disable`: Diese Anweisung legt die Nullable-Anmerkungskontexte und -Warnungskontexte auf *deaktiviert* fest.</span><span class="sxs-lookup"><span data-stu-id="30ce1-111">`#nullable disable`: Sets the nullable annotation and warning contexts to *disabled*.</span></span>
- <span data-ttu-id="30ce1-112">`#nullable enable`: Diese Anweisung legt die Nullable-Anmerkungskontexte und -Warnungskontexte auf *aktiviert* fest.</span><span class="sxs-lookup"><span data-stu-id="30ce1-112">`#nullable enable`: Sets the nullable annotation and warning contexts to *enabled*.</span></span>
- <span data-ttu-id="30ce1-113">`#nullable restore`: Diese Anweisung stellt die Nullable-Anmerkungskontexte und -Warnungskontexte der Projekteinstellungen wieder her.</span><span class="sxs-lookup"><span data-stu-id="30ce1-113">`#nullable restore`: Restores the nullable annotation and warning contexts to project settings.</span></span>
- <span data-ttu-id="30ce1-114">`#nullable disable annotations`: Diese Anweisung legt den Nullable-Anmerkungskontext auf *deaktiviert* fest.</span><span class="sxs-lookup"><span data-stu-id="30ce1-114">`#nullable disable annotations`: Sets the nullable annotation context to *disabled*.</span></span>
- <span data-ttu-id="30ce1-115">`#nullable enable annotations`: Diese Anweisung legt den Nullable-Anmerkungskontext auf *aktiviert* fest.</span><span class="sxs-lookup"><span data-stu-id="30ce1-115">`#nullable enable annotations`: Sets the nullable annotation context to *enabled*.</span></span>
- <span data-ttu-id="30ce1-116">`#nullable restore annotations`: Diese Anweisung stellt den Nullable-Anmerkungskontext der Projekteinstellungen wieder her.</span><span class="sxs-lookup"><span data-stu-id="30ce1-116">`#nullable restore annotations`: Restores the nullable annotation context to project settings.</span></span>
- <span data-ttu-id="30ce1-117">`#nullable disable warnings`: Diese Anweisung legt den Nullable-Warnungskontext auf *deaktiviert* fest.</span><span class="sxs-lookup"><span data-stu-id="30ce1-117">`#nullable disable warnings`: Sets the nullable warning context to *disabled*.</span></span>
- <span data-ttu-id="30ce1-118">`#nullable enable warnings`: Diese Anweisung legt den Nullable-Warnungskontext auf *aktiviert* fest.</span><span class="sxs-lookup"><span data-stu-id="30ce1-118">`#nullable enable warnings`: Sets the nullable warning context to *enabled*.</span></span>
- <span data-ttu-id="30ce1-119">`#nullable restore warnings`: Diese Anweisung stellt den Nullable-Warnungskontext der Projekteinstellungen wieder her.</span><span class="sxs-lookup"><span data-stu-id="30ce1-119">`#nullable restore warnings`: Restores the nullable warning context to project settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="30ce1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30ce1-120">See also</span></span>

- [<span data-ttu-id="30ce1-121">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="30ce1-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="30ce1-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="30ce1-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="30ce1-123">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="30ce1-123">C# Preprocessor Directives</span></span>](./index.md)
