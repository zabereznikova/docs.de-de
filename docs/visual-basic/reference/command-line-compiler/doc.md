---
title: -doc
ms.date: 03/10/2018
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
ms.openlocfilehash: 8b80629ce9b2cd62f10d9a53279b83ba41bc4ece
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097708"
---
# <a name="-doc"></a>-doc

Verarbeitet Dokumentationskommentare zu einer XML-Datei.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-doc[+ | -]  
```

oder  

```console
-doc:file  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Dies ist optional. Ein Angeben von + oder einfach `-doc` veranlasst den Compiler, Dokumentationsinformationen zu generieren und diese in eine XML-Datei zu schreiben. Ein Angeben von `-` entspricht dem Fehlen von `-doc`, sodass keine Dokumentationsinformationen erstellt werden.|  
|`file`|Erforderlich, wenn `-doc:` verwendet wird. Gibt die XML-Ausgabedatei an, die mit den Kommentaren aus den Quellcodedateien der Kompilierung aufgefüllt wird. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen (" ") setzen.|  
  
## <a name="remarks"></a>Hinweise  

 Die `-doc`-Option steuert, ob der Compiler eine XML-Datei generiert, die die Dokumentationskommentare enthält. Wenn Sie die `-doc:file`-Syntax verwenden, gibt der `file`-Parameter den Namen der XML-Datei an. Wenn Sie `-doc` oder `-doc+` verwenden, übernimmt der Compiler den Namen der XML-Datei von der ausführbaren Datei oder Bibliothek, die vom Compiler erstellt wird. Wenn Sie `-doc-` verwenden oder die `-doc`-Option nicht angeben, erstellt der Compiler keine XML-Datei.  
  
 In Quellcodedateien können Dokumentationskommentare den folgenden Definitionen vorangestellt sein:  
  
- Benutzerdefinierte Typen wie [Class](../../language-reference/statements/class-statement.md) und [Interface](../../language-reference/statements/interface-statement.md)  
  
- Member, z. B. ein Feld, ein Ereignis ([Event](../../language-reference/statements/event-statement.md)), eine Eigenschaft ([Property](../../language-reference/statements/property-statement.md)), eine Funktion ([Function](../../language-reference/statements/function-statement.md)) oder eine Unterroutine ([Sub](../../language-reference/statements/sub-statement.md)).  
  
 Wenn Sie die generierte XML-Datei mit der [IntelliSense](/visualstudio/ide/using-intellisense)-Funktionalität von Visual Studio verwenden möchten, geben Sie für die XML-Datei genau den Dateinamen an, den die Assembly hat, die Sie unterstützen möchten. Stellen Sie sicher, dass sich die XML-Datei im selben Verzeichnis wie die Assembly befindet, sodass auch die XML-Datei gefunden wird, wenn im Visual Studio-Projekt auf die Assembly verwiesen wird. XML-Dokumentationsdateien sind nicht erforderlich, damit IntelliSense für Code in einem Projekt oder in Projekten funktioniert, auf die in einem Projekt verwiesen wird.  
  
 Sofern Sie nicht mit `-target:module` kompilieren, enthält die XML-Datei die Tags `<assembly></assembly>`. Diese Tags geben den Namen der Datei an, die das Assemblymanifest für die Ausgabedatei der Kompilierung enthält.  
  
 Informationen zu den Möglichkeiten, wie Dokumentation aus Kommentaren in Ihrem Code generiert werden kann, finden Sie unter [XML-Kommentartags](../../language-reference/xmldoc/index.md).  
  
|So legen Sie „-doc“ in der integrierten Visual Studio-Entwicklungsumgebung fest|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Legen Sie den Wert im Feld **XML-Dokumentationsdatei generieren** fest.|  
  
## <a name="example"></a>Beispiel  

 Ein Beispiel finden Sie unter [Dokumentieren von Code mit XML](../../programming-guide/program-structure/documenting-your-code-with-xml.md).  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Dokumentieren von Code mit XML](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
