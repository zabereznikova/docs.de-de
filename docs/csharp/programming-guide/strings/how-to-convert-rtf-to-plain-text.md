---
title: 'Gewusst wie: Konvertieren vom RTF- ins Nur-Text-Format (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], converting from RTF
ms.assetid: 3b386a87-899d-4d98-bc82-a980526ddaac
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e4c7b48467f3b260526c604fa3a36fc5d80374e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-rtf-to-plain-text-c-programming-guide"></a><span data-ttu-id="41d4f-102">Gewusst wie: Konvertieren vom RTF- ins Nur-Text-Format (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="41d4f-102">How to: Convert RTF to Plain Text (C# Programming Guide)</span></span>
<span data-ttu-id="41d4f-103">Rich Text Format (RTF) ist ein Dokumentformat, das von Microsoft in den späten 1980ern entwickelt wurde, um den Austausch von Dokumenten zwischen Betriebssystemen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="41d4f-103">Rich Text Format (RTF) is a document format developed by Microsoft in the late 1980s to enable the exchange of documents across operating systems.</span></span> <span data-ttu-id="41d4f-104">Sowohl Microsoft Word als auch WordPad können RTF-Dokumente lesen und schreiben.</span><span class="sxs-lookup"><span data-stu-id="41d4f-104">Both Microsoft Word and WordPad can read and write RTF documents.</span></span> <span data-ttu-id="41d4f-105">In .NET Framework können Sie mit dem Steuerelement <xref:System.Windows.Forms.RichTextBox> ein Textverarbeitungsprogramm erstellen, das RTF unterstützt und einem Benutzer die Formatierung von Text in WYSIWIG ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="41d4f-105">In the .NET Framework, you can use the <xref:System.Windows.Forms.RichTextBox> control to create a word processor that supports RTF and enables a user to apply formatting to text in a WYSIWIG manner.</span></span>  
  
 <span data-ttu-id="41d4f-106">Sie können auch das Steuerelement <xref:System.Windows.Forms.RichTextBox> verwenden, um die RTF-Formatierungscodes aus einem Dokument programmgesteuert zu entfernen und es in reinen Text umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="41d4f-106">You can also use the <xref:System.Windows.Forms.RichTextBox> control to programmatically remove the RTF formatting codes from a document and convert it to plain text.</span></span> <span data-ttu-id="41d4f-107">Sie müssen das Steuerelement nicht in Windows Form einbetten, um diesen Vorgang durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="41d4f-107">You do not need to embed the control in a Windows Form to perform this kind of operation.</span></span>  
  
### <a name="to-use-the-richtextbox-control-in-a-project"></a><span data-ttu-id="41d4f-108">Verwenden des Steuerelements „RichTextBox“ in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="41d4f-108">To use the RichTextBox control in a project</span></span>  
  
1.  <span data-ttu-id="41d4f-109">Fügen Sie einen Verweis auf „System.Windows.Forms.dll“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="41d4f-109">Add a reference to System.Windows.Forms.dll.</span></span>  
  
2.  <span data-ttu-id="41d4f-110">Fügen Sie eine using-Anweisung für den Namespace `System.Windows.Forms` hinzu (optional).</span><span class="sxs-lookup"><span data-stu-id="41d4f-110">Add a using directive for the `System.Windows.Forms` namespace (optional).</span></span>  
  
## <a name="example"></a><span data-ttu-id="41d4f-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41d4f-111">Example</span></span>  
 <span data-ttu-id="41d4f-112">Im folgenden Beispiel wird eine Beispiel-RTF-Datei in reinen Text konvertiert.</span><span class="sxs-lookup"><span data-stu-id="41d4f-112">The following example converts a sample RTF file to plain text.</span></span> <span data-ttu-id="41d4f-113">Die Datei enthält RTF-Formatierungen (wie Schriftartinformationen), vier Unicode-Zeichen und vier erweiterte ASCII-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="41d4f-113">The file contains RTF formatting (such as font information), four Unicode characters, and four extended ASCII characters.</span></span> <span data-ttu-id="41d4f-114">Der Beispielcode öffnet die Datei, übergibt dessen Inhalt als RTF an <xref:System.Windows.Forms.RichTextBox>, ruft den Inhalt als Text ab, zeigt den Text in einer <xref:System.Windows.Forms.MessageBox> an und gibt den Text im UTF-8-Format in eine Datei aus.</span><span class="sxs-lookup"><span data-stu-id="41d4f-114">The example code opens the file, passes its content to a <xref:System.Windows.Forms.RichTextBox> as RTF, retrieves the content as text, displays the text in a <xref:System.Windows.Forms.MessageBox>, and outputs the text to a file in UTF-8 format.</span></span>  
  
 <span data-ttu-id="41d4f-115">Die `MessageBox` und die Ausgabedatei enthalten den folgenden Text:</span><span class="sxs-lookup"><span data-stu-id="41d4f-115">The `MessageBox` and the output file contain the following text:</span></span>  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
```  
  
 <span data-ttu-id="41d4f-116">[!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="41d4f-116">[!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]</span></span>  
  
 <span data-ttu-id="41d4f-117">RTF-Zeichen werden in acht Bits codiert.</span><span class="sxs-lookup"><span data-stu-id="41d4f-117">RTF characters are encoded in eight bits.</span></span> <span data-ttu-id="41d4f-118">Allerdings können Benutzer Unicode-Zeichen zusätzlich zu erweiterten ASCII-Zeichen aus angegebenen Codeseiten angeben.</span><span class="sxs-lookup"><span data-stu-id="41d4f-118">However, users can specify Unicode characters in addition to extended ASCII characters from specified code pages.</span></span> <span data-ttu-id="41d4f-119">Da die Eigenschaft <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> vom Typ [Zeichenfolge](../../../csharp/language-reference/keywords/string.md) ist, werden die Zeichen als Unicode UTF-16 codiert.</span><span class="sxs-lookup"><span data-stu-id="41d4f-119">Because the <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> property is of type [string](../../../csharp/language-reference/keywords/string.md), the characters are encoded as Unicode UTF-16.</span></span> <span data-ttu-id="41d4f-120">Alle erweiterten ASCII- und Unicode-Zeichen aus dem RTF-Quelldokument werden in der Textausgabe ordnungsgemäß codiert.</span><span class="sxs-lookup"><span data-stu-id="41d4f-120">Any extended ASCII characters and Unicode characters from the source RTF document are correctly encoded in the text output.</span></span>  
  
 <span data-ttu-id="41d4f-121">Falls Sie die Methode <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> zum Schreiben von Text auf die Festplatte verwenden, wird der Text als UTF-8 (ohne Bytereihenfolge-Marke) codiert.</span><span class="sxs-lookup"><span data-stu-id="41d4f-121">If you use the <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> method to write the text to disk, the text will be encoded as UTF-8 (without a Byte Order Mark).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d4f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41d4f-122">See Also</span></span>  
 <span data-ttu-id="41d4f-123"><xref:System.Windows.Forms.RichTextBox?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="41d4f-123"><xref:System.Windows.Forms.RichTextBox?displayProperty=fullName></span></span>   
 [<span data-ttu-id="41d4f-124">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="41d4f-124">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

