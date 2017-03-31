---
title: "#pragma-Prüfsumme (C#-Referenz) | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma checksum'
dev_langs:
- CSharp
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
caps.latest.revision: 11
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
ms.openlocfilehash: 5daf71faea5736036e9e3e0178e84ea03c314ff6
ms.lasthandoff: 03/13/2017

---
# <a name="pragma-checksum-c-reference"></a>#pragma-Prüfsumme (C#-Referenz)
Erstellt für Quelldateien Prüfsummen, um beim Debuggen von [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)]-Seiten zu helfen.  
  
## <a name="syntax"></a>Syntax  
  
```  
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a>Parameter  
 `"filename"`  
 Der Name der Datei, die die Überwachung von Änderungen oder Updates erfordert  
  
 `"{guid}"`  
 Der GUID (Globally Unique Identifier, globaler eindeutiger Bezeichner) für die Datei  
  
 `"checksum_bytes"`  
 Die Zeichenfolge von hexadezimalen Ziffern, die die Bytes der Prüfsumme darstellt. Dabei muss es sich um eine gerade Anzahl hexadezimaler Ziffern handeln. Eine ungerade Anzahl von Ziffern führt zu einer Warnung zur Kompilierzeit, und die Anweisung wird ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Der Visual Studio-Debugger verwendet eine Prüfsumme, um sicherzustellen, dass immer die richtige Quelle gefunden wird. Der Compiler berechnet die Prüfsumme für eine Quelldatei, und speichert das Ergebnis in der Program Database-Datei (PDB). Der Debugger verwendet anschließend die PDB-Datei, um sie mit der Prüfsumme zu vergleichen, die für die Quelldatei berechnet wird.  
  
 Diese Lösung funktioniert nicht bei [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)]-Projekten, weil die berechnete Prüfsumme für die generierte Quelldatei anstatt für die ASPX-Datei ist. `#pragma checksum` stellt für [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)]-Seiten Unterstützung von Prüfsummen bereit, um dieses Problem zu behandeln.  
  
 Wenn Sie ein [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)]-Projekt in [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)] erstellen, enthält die generierte Quelldatei eine Prüfsumme für die ASPX-Datei, von der die Quelle erzeugt wird. Der Compiler schreibt anschließend diese Informationen in die PDB-Datei.  
  
 Wenn der Compiler keine `#pragma checksum`-Direktive in der Datei findet, berechnet er die Prüfsumme und schreibt den Wert in die PDB-Datei.  
  
## <a name="example"></a>Beispiel  
  
```  
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{3673e4ca-6098-4ec1-890f-8fceb2a794a2}" "{012345678AB}" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)
