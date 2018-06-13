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
ms.openlocfilehash: 6b64372d4b6063da85739e939bb33abd4650ecb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651556"
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
|`+` &#124; `-`|Dies ist optional. Angeben von +, oder nur `-doc`, bewirkt, dass der Compiler Dokumentationsinformationen generieren und in eine XML-Datei zu speichern. Angeben von `-` entspricht der Angabe von nicht `-doc`, verursachen keine Dokumentationsinformationen erstellt werden.|  
|`file`|Erforderlich, wenn `-doc:` verwendet wird. Gibt die XML-Ausgabedatei, die mit den Kommentaren in den Quellcodedateien der Kompilierung aufgefüllt wird. Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").|  
  
## <a name="remarks"></a>Hinweise  
 Die `-doc` option steuert, ob der Compiler eine XML-Datei generiert, die die Dokumentationskommentare enthält. Bei Verwendung der `-doc:file` Syntax, die `file` Parameter gibt den Namen der XML-Datei. Bei Verwendung von `-doc` oder `-doc+`, nimmt der Compiler den Namen der XML-Datei aus der ausführbaren Datei oder Bibliothek, die der Compiler erstellt wird. Bei Verwendung von `-doc-` , oder geben Sie die `-doc` -Option der Compiler erstellt keine XML-Datei.  
  
 In den Quellcodedateien können die folgenden Definitionen von Dokumentationskommentare vorangestellt sein:  
  
-   Benutzerdefinierte Typen, z. B. eine [Klasse](../../../visual-basic/language-reference/statements/class-statement.md) oder [Schnittstelle](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Elemente, z. B. ein Feld [Ereignis](../../../visual-basic/language-reference/statements/event-statement.md), [Eigenschaft](../../../visual-basic/language-reference/statements/property-statement.md), [Funktion](../../../visual-basic/language-reference/statements/function-statement.md), oder [Unterroutine](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Verwenden Sie die generierte XML-Datei mit dem Visual Studio [IntelliSense](/visualstudio/ide/using-intellisense) feature, lassen Sie den Dateinamen der XML-Datei der Assembly identisch sein, Sie unterstützen möchten. Stellen Sie sicher, dass die XML-Datei im gleichen Verzeichnis wie die Assembly ist, wenn die Assembly in Visual Studio-Projekt verwiesen wird, sowie die XML-Datei gefunden wird. XML-Dokumentationsdateien sind nicht erforderlich, damit IntelliSense funktioniert für Code in einem Projekt oder in Projekten, die von einem Projekt verwiesen wird.  
  
 Wenn beim Kompilieren mit `/target:module`, die XML-Datei enthält die Tags `<assembly></assembly>`. Diese Tags Geben Sie den Namen der Datei, die das Assemblymanifest für die Ausgabedatei der Kompilierung enthält.  
  
 Finden Sie unter [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) für Methoden zum Generieren von Dokumentation von den Kommentaren im Code.  
  
|Festzulegende - integriert Doc in Visual Studio-Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Legen Sie den Wert der **generieren XML-Dokumentationsdatei** Feld.|  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) ein Beispiel.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
