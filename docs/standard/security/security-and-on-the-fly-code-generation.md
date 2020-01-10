---
title: Sicherheit und dynamische Codegenerierung
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- code security, on-the-fly code generation
- on-the-fly code generation
- security [.NET Framework], on-the-fly code generation
- secure coding, on-the-fly code generation
ms.assetid: 6d221724-bb21-4d76-90c3-0ee2a2e69be2
ms.openlocfilehash: 64ddcc6a379e5719eb734eede13e576a707696fe
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705885"
---
# <a name="security-and-on-the-fly-code-generation"></a><span data-ttu-id="2c44d-102">Sicherheit und dynamische Codegenerierung</span><span class="sxs-lookup"><span data-stu-id="2c44d-102">Security and On-the-Fly Code Generation</span></span>
<span data-ttu-id="2c44d-103">Einige Bibliotheken funktionieren, indem sie Code generieren und diesen ausführen, um einen Vorgang für den Aufrufer durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="2c44d-103">Some libraries operate by generating code and running it to perform some operation for the caller.</span></span> <span data-ttu-id="2c44d-104">Das Grundproblem besteht darin, Code auf Veranlassung eines weniger vertrauenswürdigen Codes zu generieren und den generierten Code mit einer höheren Vertrauensebene auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2c44d-104">The basic problem is generating code on behalf of lesser-trust code and running it at a higher trust.</span></span> <span data-ttu-id="2c44d-105">Das Problem ist noch gravierender, wenn der Aufrufer die Codegenerierung beeinflussen kann. Deshalb müssen Sie sicherstellen, dass nur Code generiert wird, den Sie als sicher erachten.</span><span class="sxs-lookup"><span data-stu-id="2c44d-105">The problem worsens when the caller can influence code generation, so you must ensure that only code you consider safe is generated.</span></span>  
  
 <span data-ttu-id="2c44d-106">Sie müssen jederzeit genau wissen, welchen Code Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="2c44d-106">You need to know exactly what code you are generating at all times.</span></span> <span data-ttu-id="2c44d-107">Dies bedeutet, dass Sie unbedingte Kontrolle über alle Werte haben müssen, die von einem Benutzer stammen, egal, ob diese Werte in Anführungszeichen eingeschlossene Zeichenfolgen (die mit Escapezeichen versehen werden sollten, damit sie keine unerwarteten Codeelemente enthalten können), Bezeichner (die daraufhin überprüft werden sollten, dass sie gültige Bezeichner sind) oder etwas anderes sind.</span><span class="sxs-lookup"><span data-stu-id="2c44d-107">This means that you must have strict controls on any values that you get from a user, be they quote-enclosed strings (which should be escaped so they cannot include unexpected code elements), identifiers (which should be checked to verify that they are valid identifiers), or anything else.</span></span> <span data-ttu-id="2c44d-108">Bezeichner können gefährlich sein, da eine kompilierte Assembly so geändert werden kann, dass ihre Bezeichner ungewöhnliche Zeichen enthalten, die die Assembly wahrscheinlich unbrauchbar machen (obwohl dies selten ein Sicherheitsrisiko darstellt).</span><span class="sxs-lookup"><span data-stu-id="2c44d-108">Identifiers can be dangerous because a compiled assembly can be modified so that its identifiers contain strange characters, which will probably break it (although this is rarely a security vulnerability).</span></span>  
  
 <span data-ttu-id="2c44d-109">Es wird empfohlen, dass Sie Code mit Reflektionsausgabe generieren, wodurch sich viele dieser Probleme vermeiden lassen.</span><span class="sxs-lookup"><span data-stu-id="2c44d-109">It is recommended that you generate code with reflection emit, which often helps you avoid many of these problems.</span></span>  
  
 <span data-ttu-id="2c44d-110">Wenn Sie den Code kompilieren, sollten Sie überlegen, ob für Malware eine Möglichkeit besteht, den Code zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2c44d-110">When you compile the code, consider whether there is some way a malicious program could modify it.</span></span> <span data-ttu-id="2c44d-111">Gibt es ein kleines Zeitfenster, in dem Malware den Quellcode auf dem Datenträger ändern kann, bevor der Quellcode vom Compiler gelesen wird oder bevor Ihr Code die DLL-Datei lädt?</span><span class="sxs-lookup"><span data-stu-id="2c44d-111">Is there a small window of time during which malicious code can change source code on disk before the compiler reads it or before your code loads the .dll file?</span></span> <span data-ttu-id="2c44d-112">Ist dies der Fall, müssen Sie das Verzeichnis, das diese Dateien enthält, entsprechend mit einer Zugriffssteuerungsliste im Dateisystem schützen.</span><span class="sxs-lookup"><span data-stu-id="2c44d-112">If so, you must protect the directory containing these files, using an Access Control List in the file system, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c44d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c44d-113">See also</span></span>

- [<span data-ttu-id="2c44d-114">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="2c44d-114">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
