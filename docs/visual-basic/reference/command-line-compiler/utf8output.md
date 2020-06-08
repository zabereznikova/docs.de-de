---
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 0a16cdc535de5ed0619bf080bb4637449b11cfef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403056"
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
Zeigt die Compilerausgabe mit UTF-8-Codierung an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
 `+` &#124; `-`  
 Dies ist optional. Der Standardwert für diese Option ist `-utf8output-`. Dies bedeutet, dass die Compilerausgabe keine UTF-8-Codierung verwendet. Die Angabe von `-utf8output` ist mit der Angabe von `-utf8output+` identisch.  
  
## <a name="remarks"></a>Hinweise  
 Bei einigen internationalen Konfigurationen kann die Compilerausgabe nicht ordnungsgemäß in der Konsole angezeigt werden. Verwenden Sie in solchen Situationen `-utf8output`, und leiten Sie die Compilerausgabe an eine Datei weiter.  
  
> [!NOTE]
> Diese Option `-utf8output` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `In.vb` und weist den Compiler an, die Ausgabe mithilfe der UTF-8-Codierung anzuzeigen.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](index.md)
- [Beispiele für Kompilierungsbefehlszeilen](sample-compilation-command-lines.md)
