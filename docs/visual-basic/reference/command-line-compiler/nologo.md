---
title: -nologo (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: bb64a468f67745b80b47b42c4fac18852279035d
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005424"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)
Unterdrückt die Anzeige der Copyright Banner und Informationsmeldungen während der Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie `-nologo` angeben, wird vom Compiler kein Copyright Banner angezeigt. In der Standardeinstellung ist `-nologo` nicht aktiv.  
  
> [!NOTE]
> Die Option "`-nologo`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird `T2.vb` kompiliert, und es wird kein Copyright Banner angezeigt.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
