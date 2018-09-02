---
title: -Doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c77d063d64354bf4693ce82509f36be9d2e5b0c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43399776"
---
# <a name="-doc"></a>-Doc
Verarbeitet Dokumentationskommentare zu einer XML-Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Dies ist optional. Angeben von +, oder nur `-doc`, generiert der Compiler generieren, und platzieren Sie es in eine XML-Datei. Angeben von `-` entspricht der Angabe nicht `-doc`, verursacht keine Dokumentationsinformationen erstellt werden.|  
|`file`|Erforderlich, wenn `-doc:` verwendet wird. Gibt die XML-Ausgabedatei, die mit den Kommentaren in den Quellcodedateien der Kompilierung aufgefüllt wird. Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").|  
  
## <a name="remarks"></a>Hinweise  
 Die `-doc` option steuert, ob der Compiler eine XML-Datei generiert, die die Dokumentationskommentare enthält. Bei Verwendung der `-doc:file` Syntax, die `file` Parameter gibt den Namen der XML-Datei. Bei Verwendung von `-doc` oder `-doc+`, nimmt der Compiler den Namen der XML-Datei aus der ausführbaren Datei oder Bibliothek, die die vom Compiler erstellt wird. Bei Verwendung von `-doc-` , oder geben Sie nicht die `-doc` auswählen, erstellt der Compiler keine XML-Datei.  
  
 Dokumentationskommentare in Quellcodedateien, können die folgenden Definitionen voranstellen:  
  
-   Benutzerdefinierte Typen, z. B. eine [Klasse](../../../visual-basic/language-reference/statements/class-statement.md) oder [Schnittstelle](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Member, z. B. ein Feld, [Ereignis](../../../visual-basic/language-reference/statements/event-statement.md), [Eigenschaft](../../../visual-basic/language-reference/statements/property-statement.md), [Funktion](../../../visual-basic/language-reference/statements/function-statement.md), oder [Unterroutine](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Verwenden Sie die generierte XML-Datei mit dem Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, können Sie den Dateinamen der XML-Datei der Assembly identisch sein, Sie unterstützen möchten. Stellen Sie sicher, dass die XML-Datei im gleichen Verzeichnis wie die Assembly ist, wenn die Assembly in Visual Studio-Projekt verwiesen wird, sowie die XML-Datei gefunden wird. XML-Dokumentationsdateien sind nicht erforderlich, damit IntelliSense funktioniert für Code in einem Projekt oder innerhalb von Projekten, die von einem Projekt verwiesen wird.  
  
 Wenn Sie die Kompilierung mit `/target:module`, die XML-Datei enthält die Tags `<assembly></assembly>`. Diese Tags Geben Sie den Namen der Datei mit dem Assemblymanifest für die Ausgabedatei der Kompilierung.  
  
 Finden Sie unter [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md) Möglichkeiten zum Generieren von Dokumentation aus Kommentaren in Ihrem Code.  
  
|Set - integriert Doc in Visual Studio-Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Legen Sie den Wert der **XML-Dokumentationsdatei generieren** Feld.|  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Documenting Your Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) ein Beispiel.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
