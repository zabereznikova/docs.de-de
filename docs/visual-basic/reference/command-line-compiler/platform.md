---
title: -platform
ms.date: 03/13/2018
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
ms.openlocfilehash: a6226b73d5d5d4d48a71afe39e8a546019d4c0bc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352345"
---
# <a name="-platform-visual-basic"></a>-Platform (Visual Basic)
Gibt an, welche Plattformversion der common Language Runtime (CLR) die Ausgabedatei ausführen kann.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`x86`|Kompiliert die Assembly für die 32-Bit-x86-kompatible CLR (Common Language Runtime).|  
|`x64`|Kompiliert Ihre Assembly für die 64-Bit-CLR auf einem Computer, der den AMD64- oder EM64T-Anweisungssatz unterstützt.|  
|`Itanium`|Kompiliert Ihre Assembly für die Ausführung durch den 64-Bit-CLR auf einem Computer mit einem Itanium-Prozessor.|  
|`arm`|Kompiliert Ihre Assembly für die Ausführung auf einem Computer mit einem ARM-Prozessor (Advanced RISC-Computer).|  
|`anycpu`|Kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform. Die Anwendung wird auf 32-Bit-Versionen von Windows als 32-Bit-Anwendung und auf 64-Bit-Versionen von Windows als 64-Bit-Anwendung ausgeführt. Diese Meldung ist der Standardwert.|  
|`anycpu32bitpreferred`|Kompiliert die Assembly für die Ausführung auf einer beliebigen Plattform. Die Anwendung wird als 32-Bit-Anwendung auf 32-Bit- und 64-Bit-Versionen von Windows ausgeführt. Dieses Flag gilt nur für ausführbare Dateien (. EXE) und erfordert .NET Framework 4,5.|  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die `-platform`-Option, um den Typ des Zielprozessors für die Ausgabedatei anzugeben.  
  
 Im Allgemeinen werden in Visual Basic geschriebene .NET Framework-Assemblys identisch ausgeführt, unabhängig von der Plattform. Es gibt jedoch einige Fälle, die sich auf unterschiedlichen Plattformen unterschiedlich verhalten. Diese allgemeinen Fälle sind:  
  
- Strukturen, die Member enthalten, deren Größe sich je nach Plattform ändert (z. B. jeder beliebige Zeigertyp).  
  
- Zeigerarithmetik, die Größen von Konstanten einschließt.  
  
- Fehlerhafter Plattformaufruf oder COM-Deklarationen, die `Integer` statt <xref:System.IntPtr> für Handles verwenden.  
  
- Umwandeln von <xref:System.IntPtr> zu `Integer`.  
  
- Verwendet einen Plattformaufruf oder COM-Interop für Komponenten, die nicht auf allen Plattformen vorhanden sind.  
  
 Die Option **-Platform** minimiert einige Probleme, wenn Sie wissen, dass Sie Annahmen über die Architektur gemacht haben, in der Ihr Code ausgeführt wird. Dies gilt insbesondere in folgenden Fällen:  
  
- Wenn Sie sich entscheiden, eine 64-Bit-Plattform anzuzielen und die Anwendung auf einem 32-Bit-Computer ausgeführt wird, wird die Fehlermeldung sehr viel früher angezeigt und ist mehr problemorientiert als eine Fehlermeldung, die auftritt, wenn dieser Switch nicht verwendet wird.  
  
- Wenn Sie die `x86`-Flag in der Option festlegen und anschließend die Anwendung auf einem 64-Bit-Computer ausgeführt wird, wird die Anwendung im WOW-Subsystem statt nativ ausgeführt.  
  
 Auf einem 64-Bit-Windows-Betriebssystem:  
  
- Kompilierte Assemblys mit `-platform:x86` werden in der 32-Bit-CLR unter WOW64 ausgeführt.  
  
- Kompilierte ausführbare Dateien mit dem `-platform:anycpu` werden in der 64-Bit-CLR ausgeführt.  
  
- Eine mit der `-platform:anycpu` kompilierte DLL wird in derselben CLR wie der Prozess, in den sie geladen wurde, ausgeführt.  
  
- Ausführbare Dateien, die mit `-platform:anycpu32bitpreferred` kompiliert werden, werden in der 32-Bit-CLR ausgeführt.  
  
 Weitere Informationen zum Entwickeln einer Anwendung, die auf einer 64-Bit-Version von Windows ausgeführt wird, finden Sie unter [64-Bit-Anwendungen](../../../framework/64-bit-apps.md).  
  
### <a name="to-set--platform-in-the-visual-studio-ide"></a>So legen Sie-Platform in der Visual Studio-IDE fest  
  
1. Wählen Sie in **Projektmappen-Explorer**das Projekt aus, öffnen Sie das Menü **Projekt** , und klicken Sie dann auf **Eigenschaften**.  
  
2. Aktivieren bzw. deaktivieren Sie auf der Registerkarte **Kompilieren** das Kontrollkästchen **32-Bit bevorzugen** , oder wählen Sie in der Liste **Ziel-CPU** einen Wert aus.  
  
     Weitere Informationen finden Sie unter [Seite "kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht, wie die `-platform`-Compileroption genutzt wird.  
  
```console
vbc -platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [-Target (Visual Basic)](target.md)
- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
