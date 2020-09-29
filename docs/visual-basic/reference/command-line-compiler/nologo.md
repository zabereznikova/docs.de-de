---
title: -nologo
ms.date: 03/13/2018
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
ms.openlocfilehash: 5557d681c5e6901592936efd35b3c552d43e39b0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097669"
---
# <a name="-nologo-visual-basic"></a>-nologo (Visual Basic)

Unterdrückt die Anzeige von Copyrightbannern und Informationsmeldungen während der Kompilierung  
  
## <a name="syntax"></a>Syntax  
  
```console  
-nologo  
```  
  
## <a name="remarks"></a>Hinweise  

 Wenn Sie `-nologo` angeben, zeigt der Compiler keine Copyrightbanner an. In der Standardeinstellung ist `-nologo` nicht aktiv.  
  
> [!NOTE]
> Die Option `-nologo` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  

 Mit dem folgenden Code wird `T2.vb` kompiliert und kein Copyrightbanner angezeigt.  
  
```console
vbc -nologo t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
