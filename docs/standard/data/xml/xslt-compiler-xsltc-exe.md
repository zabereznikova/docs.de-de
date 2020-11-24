---
title: XSLT-Compiler (xsltc.exe)
ms.date: 03/30/2017
ms.assetid: 672a5ac8-8305-4d28-ba10-11089c2c0924
ms.openlocfilehash: cfeebc3ac0c0259c975439dc93c3c5f003b60c40
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94818322"
---
# <a name="xslt-compiler-xsltcexe"></a>XSLT-Compiler (xsltc.exe)
Der XSLT-Compiler (xsltc.exe) kompiliert XSLT-Stylesheets und generiert eine Assembly. Das kompilierte Stylesheet kann dann direkt in die <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>-Methode übergeben werden. Sie können mit xsltc.exe keine signierten Assemblys generieren.  
  
 Das Tool „xsltc.exe“ ist Bestandteil von Visual Studio. Weitere Informationen finden Sie bei den [Visual Studio-Downloads](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).  
  
## <a name="syntax"></a>Syntax  
  
```console  
xsltc [options] [/class:<name>] <sourceFile> [[/class:<name>] <sourceFile>...]  
```  
  
## <a name="argument"></a>Argument  
  
|Argument|Beschreibung|  
|--------------|-----------------|  
|`sourceFile`|Gibt den Namen des Stylesheets an. Das Stylesheet muss eine lokale Datei sein oder sich im Intranet befinden.|  
  
## <a name="options"></a>Optionen  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`/c[lass]:` `name`|Gibt den Namen der Klasse für das folgende Stylesheet an. Der Klassenname kann vollqualifiziert sein.<br /><br /> In der Standardeinstellung ist der Klassenname mit dem Namen des Stylesheets identisch. Wenn zum Beispiel das Stylesheet customers.xsl kompiliert wird, lautet der standardmäßige Klassenname customers.|  
|`/debug[`+&#124;-`]`|Gibt an, ob Debuginformationen generiert werden sollen.<br /><br /> Wenn `+` oder `/debug` angegeben wird, generiert der Compiler Debuginformationen und speichert sie in einer Programmdatenbankdatei (PDB-Datei). Der Name der generierten PDB-Datei lautet `assemblyName`.pdb.<br /><br /> Wenn Sie `-` angeben, was im Endeffekt dasselbe ist, wie `/debug` nicht anzugeben, werden keine Debuginformationen erstellt. Es wird eine Retailassembly generiert. **Hinweis**:  Beim Kompilieren im Debugmodus kann sich die XSLT-Geschwindigkeit spürbar verringern.|  
|`/help`|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|`/nologo`|Unterdrückt die Anzeige der Compilercopyrightmeldung.|  
|`/platform:` `string`|Gibt die Plattformen an, auf denen die Assembly ausgeführt werden kann. Im Folgenden werden die gültigen Plattformwerte beschrieben:<br /><br /> `x86` kompiliert die Assembly für die 32-Bit-x86-kompatible CLR (Common Language Runtime).<br /><br /> `x64` kompiliert die Assembly für die 64-Bit-CLR auf einem Computer, der den AMD64- oder EM64T-Anweisungssatz unterstützt.<br /><br /> Itanium kompiliert die Assembly für die 64-Bit-CLR auf einem Computer mit einem Itanium-Prozessor.<br /><br /> `anycpu` kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform. Dies ist die Standardeinstellung.|  
|`/out:` `assemblyName`|Gibt den Namen der Assembly an, die ausgegeben wird. Der Assemblyname entspricht standardmäßig dem Namen des Hauptstylesheets bzw. des ersten Stylesheets, falls es mehrere Stylesheets gibt.<br /><br /> Wenn das Stylesheet Skripts enthält, werden die Skripts in einer separaten Assembly gespeichert. Die Namen der Skriptassemblys werden auf der Grundlage des Namens der Hauptassembly generiert. Wenn Sie z. B. als Assemblynamen CustOrders.dll angegeben haben, wird die erste Skriptassembly CustOrders_Script1.dll genannt.|  
|`/settings:` `document+-, script+-, DTD+-,`|Gibt an, ob `document()`-Funktionen, XSLT-Skripts oder Dokumenttypdefinitionen (DTD) im Stylesheet zugelassen sind.<br /><br /> In der Standardeinstellung werden DTD, die `document()`-Funktion und Skripts nicht unterstützt.|  
|`@` `file`|Ermöglicht die Angabe einer Datei, die Compileroptionen enthält.|  
|`?`|Zeigt Befehlssyntax und Optionen für das Tool an.|  
  
## <a name="remarks"></a>Hinweise  
 XSLT-Lösungen können aus mehreren Stylesheetmodulen bestehen. Das Tool &lt;legacyBold&gt;xsltc.exe&lt;/legacyBold&gt; generiert Assemblys auf der Grundlage von Stylesheets. Die Assemblys können dann direkt in die <xref:System.Xml.Xsl.XslCompiledTransform.Load%28System.Type%29?displayProperty=nameWithType>-Methode übergeben werden. Auf diese Weise lassen sich in einigen XSLT-Bereitstellungsszenarios die zu verzeichnenden Leistungseinbußen verringern.  
  
> [!NOTE]
> Sie müssen auch die kompilierte Assembly als Verweis in die Anwendung einschließen.  
  
 Das Tool „xsltc.exe“ überprüft weder den Namen der Klasse (`/class:`*name*) noch den der Assembly (`/out:`*assemblyName*). Wenn die Namen nicht gültig sind, gibt die CLR entsprechende Fehlermeldungen aus.  
  
## <a name="examples"></a>Beispiele  
 Der folgende Befehl kompiliert das Stylesheet und erstellt eine Assembly mit dem Namen booksort.dll.  
  
```console  
xsltc booksort.xsl  
```  
  
 Der folgende Befehl kompiliert das Stylesheet und erstellt eine Assembly mit dem Namen booksort.dll und eine PDB-Datei mit dem Namen booksort.pdb.  
  
```console  
xsltc booksort.xsl /debug  
```  
  
 Der folgende Befehl kompiliert ein Stylesheet, das ein &lt;legacyBold&gt;msxsl:script&lt;/legacyBold&gt;-Element enthält, und erstellt zwei Assemblys namens &lt;legacyBold&gt;calc.dll&lt;/legacyBold&gt; und &lt;legacyBold&gt;calc_Script1.dll&lt;/legacyBold&gt;.  
  
```console  
xsltc /settings:script+ calc.xsl  
```  
  
 Der folgende Befehl aktiviert die DTD-Verarbeitung und die Unterstützung für Skripts und erstellt zwei Assemblys namens myTest.dll und myTest_Script1.dll.  
  
```console  
xsltc /settings:DTD+,script+ /out:myTest calc.xsl  
```  
  
 Der folgende Befehl kompiliert zwei Stylesheetmodule und eine Assembly mit dem Namen booksort.dll.  
  
```console  
xsltc booksort.xsl output.xsl  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Xsl.XslCompiledTransform>
- [How to: Ausführen einer XSLT-Transformation mittels einer Assembly](how-to-perform-an-xslt-transformation-by-using-an-assembly.md)
- [XSLT Transformations (XSLT-Transformationen)](xslt-transformations.md)
