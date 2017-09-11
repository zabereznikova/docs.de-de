---
title: Wert des Typs &quot;&lt;&quot;Typname1&quot;&gt;&quot;kann nicht konvertiert werden&quot;&lt;typename2&gt;&quot; | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
dev_langs:
- VB
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2fbe1550515d2b15a3e349392fc8d78812787ae4
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a><span data-ttu-id="288ec-102">Wert des Typs '&lt;"Typname1"&gt;"kann nicht konvertiert werden"&lt;typename2&gt;'</span><span class="sxs-lookup"><span data-stu-id="288ec-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="288ec-103">Wert des Typs '\<"Typname1" >' kann nicht konvertiert werden "\<typename2 >'.</span><span class="sxs-lookup"><span data-stu-id="288ec-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="288ec-104">Typenkonflikt wird möglicherweise durch das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly '\<Assemblyname >'.</span><span class="sxs-lookup"><span data-stu-id="288ec-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="288ec-105">Ersetzen Sie den Verweis auf "\<Filepath >" im Projekt "\<projectname1 >" durch einen Projektverweis auf '\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="288ec-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="288ec-106">Wenn ein Projekt sowohl einen Projektverweis als auch einen Dateiverweis enthält, kann der Compiler, dass ein Typ in einen anderen konvertiert werden kann nicht gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="288ec-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="288ec-107">Der folgende Pseudocode veranschaulicht eine Situation, die diesen Fehler verursachen kann.</span><span class="sxs-lookup"><span data-stu-id="288ec-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 <span data-ttu-id="288ec-108">Project `P1` macht einen indirekten Projektverweis über Projekt `P2` Projekt `P3`, und auch ein direkter Verweis auf `P3`.</span><span class="sxs-lookup"><span data-stu-id="288ec-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="288ec-109">Die Deklaration von `commonObject` verwendet den Dateiverweis auf `P3`, während im Aufruf von `P2.getCommonClass` verwendet den Projektverweis `P3`.</span><span class="sxs-lookup"><span data-stu-id="288ec-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="288ec-110">Das Problem in diesem Fall ist, dass im Dateiverweis ein Dateipfad und-Name für die Ausgabedatei angegeben `P3` (normalerweise p3.dll), während die Projektverweise das Quellprojekt ermitteln (`P3`) nach dem Projektnamen.</span><span class="sxs-lookup"><span data-stu-id="288ec-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="288ec-111">Aus diesem Grund der Compiler nicht garantieren, dass den Typ `P3.commonClass` demselben Quellcode über zwei unterschiedliche Verweise stammt.</span><span class="sxs-lookup"><span data-stu-id="288ec-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="288ec-112">Diese Situation tritt normalerweise auf, wenn Projektverweise und Dateiverweise gemeinsam.</span><span class="sxs-lookup"><span data-stu-id="288ec-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="288ec-113">In der vorherigen Abbildung sind das Problem würde nicht auftreten, wenn `P1` erstellt einen direkten Projektverweis auf `P3` statt eines Dateiverweises.</span><span class="sxs-lookup"><span data-stu-id="288ec-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="288ec-114">**Fehler-ID:** BC30955</span><span class="sxs-lookup"><span data-stu-id="288ec-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="288ec-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="288ec-115">To correct this error</span></span>  
  
-   <span data-ttu-id="288ec-116">Ändern Sie den Verweis auf einen Projektverweis.</span><span class="sxs-lookup"><span data-stu-id="288ec-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="288ec-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="288ec-117">See Also</span></span>  
 <span data-ttu-id="288ec-118">[Typumwandlungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="288ec-118">[Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="288ec-119"> [Verwalten von Verweise in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="288ec-119"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="288ec-120"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box (Vorgehensweise: Hinzufügen und Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“)](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span><span class="sxs-lookup"><span data-stu-id="288ec-120"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span></span>
