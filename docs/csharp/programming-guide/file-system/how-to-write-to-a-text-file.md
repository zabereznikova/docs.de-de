---
title: 'Gewusst wie: Schreiben in eine Textdatei (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
dev_langs:
- CSharp
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 12a74a5664a8f514c89d9de3ce470c98319f84d2
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a><span data-ttu-id="a438e-102">Gewusst wie: Schreiben in eine Textdatei (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a438e-102">How to: Write to a Text File (C# Programming Guide)</span></span>
<span data-ttu-id="a438e-103">In diesen Beispielen werden verschiedene Möglichkeiten veranschaulicht, Text in eine Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="a438e-103">These examples show various ways to write text to a file.</span></span>  <span data-ttu-id="a438e-104">In den ersten beiden Beispielen werden statische Hilfsmethoden für die <xref:System.IO.File?displayProperty=fullName>-Klasse verwendet, um jedes Element von „IEnumerable\<string>“ und um eine Zeichenfolge in eine Textdatei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="a438e-104">The first two examples use static convenience methods on the <xref:System.IO.File?displayProperty=fullName> class to write each element of any IEnumerable\<string> and a string to a text file.</span></span>  <span data-ttu-id="a438e-105">In Beispiel 3 wird dargestellt, wie Text einer Datei hinzugefügt wird, wenn jede Zeile beim Schreiben in die Datei einzeln verarbeitet werden muss.</span><span class="sxs-lookup"><span data-stu-id="a438e-105">Example 3 shows how to add text to a file when you have to process each line individually as you write to the file.</span></span>  <span data-ttu-id="a438e-106">Die Beispiele 1–3 überschreiben alle vorhandenen Inhalte in der Datei. In Beispiel 4 wird jedoch gezeigt, wie einer vorhandenen Datei Text angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="a438e-106">Examples 1-3 overwrite all existing content in the file, but example 4 shows you how to append text to an existing file.</span></span>  
  
 <span data-ttu-id="a438e-107">In allen diesen Beispielen werden Zeichenfolgenliterale in Dateien geschrieben. Sie sollten jedoch eher die <xref:System.String.Format%2A>-Methode verwenden, die viele Steuerelemente enthält, mit denen verschiedene Wertetypen rechts- oder linksbündig mit oder ohne Abstand in ein Feld geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="a438e-107">These examples all write string literals to files, but more likely you will want to use the <xref:System.String.Format%2A> method, which has many controls for writing different types of values  right or left justified in a field, with or without padding, and so on.</span></span>  <span data-ttu-id="a438e-108">Sie können auch die Funktion für die C#-[Zeichenfolgeninterpolierung](../../../csharp/language-reference/keywords/interpolated-strings.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a438e-108">You can also use the C# [string interpolation](../../../csharp/language-reference/keywords/interpolated-strings.md) feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a438e-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a438e-109">Example</span></span>  
 <span data-ttu-id="a438e-110">[!code-cs[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a438e-110">[!code-cs[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]</span></span>  
  
 <span data-ttu-id="a438e-111">In allen diesen Beispielen werden Zeichenfolgenliterale in Dateien geschrieben. Sie sollten jedoch eher die <xref:System.String.Format%2A>-Methode verwenden, die viele Steuerelemente enthält, mit denen verschiedene Wertetypen rechts- oder linksbündig mit oder ohne Abstand in ein Feld geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="a438e-111">These examples all write string literals to files, but more likely you will want to use the <xref:System.String.Format%2A> method, which has many controls for writing different types of values  right or left justified in a field, with or without padding, and so on.</span></span>  <span data-ttu-id="a438e-112">Sie können auch die Funktion für die C#-[Zeichenfolgeninterpolierung](../../../csharp/language-reference/keywords/interpolated-strings.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a438e-112">You can also use the C# [string interpolation](../../../csharp/language-reference/keywords/interpolated-strings.md) feature.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a438e-113">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="a438e-113">Robust Programming</span></span>  
 <span data-ttu-id="a438e-114">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="a438e-114">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="a438e-115">Die Datei ist bereits vorhanden und ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="a438e-115">The file exists and is read-only.</span></span>  
  
-   <span data-ttu-id="a438e-116">Der Pfadname ist möglicherweise zu lang.</span><span class="sxs-lookup"><span data-stu-id="a438e-116">The path name may be too long.</span></span>  
  
-   <span data-ttu-id="a438e-117">Der Datenträger ist möglicherweise voll.</span><span class="sxs-lookup"><span data-stu-id="a438e-117">The disk may be full.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a438e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a438e-118">See Also</span></span>  
 <span data-ttu-id="a438e-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a438e-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a438e-120">[Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](../../../csharp/programming-guide/file-system/index.md) </span><span class="sxs-lookup"><span data-stu-id="a438e-120">[File System and the Registry (C# Programming Guide)](../../../csharp/programming-guide/file-system/index.md) </span></span>  
 [<span data-ttu-id="a438e-121">Beispiel: Speichern einer Auflistung im Anwendungsspeicher</span><span class="sxs-lookup"><span data-stu-id="a438e-121">Sample: Save a collection to Application Storage</span></span>](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)

