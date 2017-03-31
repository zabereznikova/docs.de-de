---
title: 'Vorgehensweise: Schreiben in eine Textdatei (C#-Programmierhandbuch) | Microsoft-Dokumentation'
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c56095582561e4df19b164bc9a46b69a14da7c9d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Gewusst wie: Schreiben in eine Textdatei (C#-Programmierhandbuch)
In diesen Beispielen werden verschiedene Möglichkeiten veranschaulicht, Text in eine Datei zu schreiben.  In den ersten zwei Beispielen werden statische Hilfsmethoden für die <xref:System.IO.File?displayProperty=fullName>-Klasse verwendet, um jedes Element von „IEnumerable\<string>“ und um eine Zeichenfolge in eine Textdatei zu schreiben.  In Beispiel 3 wird dargestellt, wie Text einer Datei hinzugefügt wird, wenn jede Zeile beim Schreiben in die Datei einzeln verarbeitet werden muss.  Die Beispiele 1–3 überschreiben alle vorhandenen Inhalte in der Datei. In Beispiel 4 wird jedoch gezeigt, wie einer vorhandenen Datei Text angefügt wird.  
  
 In allen diesen Beispielen werden Zeichenfolgenliterale in Dateien geschrieben. Es ist jedoch wahrscheinlicher, dass Sie die <xref:System.String.Format%2A>-Methode verwenden möchten, die viele Steuerelemente enthält, mit denen verschiedene Wertetypen rechts- oder linksbündig mit oder ohne Abstand in ein Feld geschrieben werden können.  Sie können auch die Funktion für die C#-[Zeichenfolgeninterpolierung](../../../csharp/language-reference/keywords/interpolated-strings.md) verwenden.  
  
## <a name="example"></a>Beispiel  
 [!code-cs[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
 In allen diesen Beispielen werden Zeichenfolgenliterale in Dateien geschrieben. Es ist jedoch wahrscheinlicher, dass Sie die <xref:System.String.Format%2A>-Methode verwenden möchten, die viele Steuerelemente enthält, mit denen verschiedene Wertetypen rechts- oder linksbündig mit oder ohne Abstand in ein Feld geschrieben werden können.  Sie können auch die Funktion für die C#-[Zeichenfolgeninterpolierung](../../../csharp/language-reference/keywords/interpolated-strings.md) verwenden.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Die Datei ist bereits vorhanden und ist schreibgeschützt.  
  
-   Der Pfadname ist möglicherweise zu lang.  
  
-   Der Datenträger ist möglicherweise voll.  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](../../../csharp/programming-guide/file-system/index.md)   
 [Beispiel: Speichern einer Auflistung im Anwendungsspeicher](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
