---
title: -Nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 21c708ef632cc0ed923713cd49e22d44848b4db3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199904"
---
# <a name="-nologo-visual-basic"></a>-Nologo (Visual Basic)
Unterdrückt die Anzeige der Copyrightinformationen und informationsmeldungen während der Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
-nologo  
```  
  
## <a name="remarks"></a>Hinweise  
 Bei Angabe von `-nologo`, der Compiler nicht Copyrightinformationen angezeigt. In der Standardeinstellung ist `-nologo` nicht aktiv.  
  
> [!NOTE]
>  Die `-nologo` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` und Copyrightinformationen nicht angezeigt.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
