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
# <a name="how-to-convert-rtf-to-plain-text-c-programming-guide"></a>Gewusst wie: Konvertieren vom RTF- ins Nur-Text-Format (C#-Programmierhandbuch)
Rich Text Format (RTF) ist ein Dokumentformat, das von Microsoft in den späten 1980ern entwickelt wurde, um den Austausch von Dokumenten zwischen Betriebssystemen zu ermöglichen. Sowohl Microsoft Word als auch WordPad können RTF-Dokumente lesen und schreiben. In .NET Framework können Sie mit dem Steuerelement <xref:System.Windows.Forms.RichTextBox> ein Textverarbeitungsprogramm erstellen, das RTF unterstützt und einem Benutzer die Formatierung von Text in WYSIWIG ermöglicht.  
  
 Sie können auch das Steuerelement <xref:System.Windows.Forms.RichTextBox> verwenden, um die RTF-Formatierungscodes aus einem Dokument programmgesteuert zu entfernen und es in reinen Text umzuwandeln. Sie müssen das Steuerelement nicht in Windows Form einbetten, um diesen Vorgang durchzuführen.  
  
### <a name="to-use-the-richtextbox-control-in-a-project"></a>Verwenden des Steuerelements „RichTextBox“ in einem Projekt  
  
1.  Fügen Sie einen Verweis auf „System.Windows.Forms.dll“ hinzu.  
  
2.  Fügen Sie eine using-Anweisung für den Namespace `System.Windows.Forms` hinzu (optional).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Beispiel-RTF-Datei in reinen Text konvertiert. Die Datei enthält RTF-Formatierungen (wie Schriftartinformationen), vier Unicode-Zeichen und vier erweiterte ASCII-Zeichen. Der Beispielcode öffnet die Datei, übergibt dessen Inhalt als RTF an <xref:System.Windows.Forms.RichTextBox>, ruft den Inhalt als Text ab, zeigt den Text in einer <xref:System.Windows.Forms.MessageBox> an und gibt den Text im UTF-8-Format in eine Datei aus.  
  
 Die `MessageBox` und die Ausgabedatei enthalten den folgenden Text:  
  
```  
The Greek word for "psyche" is spelled ψυχή. The Greek letters are encoded in Unicode.  
These characters are from the extended ASCII character set (Windows code page 1252):  âäӑå  
```  
  
 [!code-cs[csProgGuideStrings#33](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-rtf-to-plain-text_1.cs)]  
  
 RTF-Zeichen werden in acht Bits codiert. Allerdings können Benutzer Unicode-Zeichen zusätzlich zu erweiterten ASCII-Zeichen aus angegebenen Codeseiten angeben. Da die Eigenschaft <xref:System.Windows.Forms.RichTextBox.Text%2A?displayProperty=fullName> vom Typ [Zeichenfolge](../../../csharp/language-reference/keywords/string.md) ist, werden die Zeichen als Unicode UTF-16 codiert. Alle erweiterten ASCII- und Unicode-Zeichen aus dem RTF-Quelldokument werden in der Textausgabe ordnungsgemäß codiert.  
  
 Falls Sie die Methode <xref:System.IO.File.WriteAllText%2A?displayProperty=fullName> zum Schreiben von Text auf die Festplatte verwenden, wird der Text als UTF-8 (ohne Bytereihenfolge-Marke) codiert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.RichTextBox?displayProperty=fullName>   
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)

