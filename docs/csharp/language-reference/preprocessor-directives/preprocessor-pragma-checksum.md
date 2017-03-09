---
title: "#pragma checksum (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#pragma checksum"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#pragma-Prüfsumme [C#]"
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# #pragma checksum (C#-Referenz)
Generiert Prüfsummen für Quelldateien, um das Debuggen von [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)]\-Seiten zu unterstützen.  
  
## Syntax  
  
```  
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### Parameter  
 `"filename"`  
 Der Name der Datei, für die eine Überwachung von Änderungen oder Aktualisierungen erforderlich ist.  
  
 `"{guid}"`  
 Die GUID \(Globally Unique Identifier\) der Datei.  
  
 `"checksum_bytes"`  
 Die Zeichenfolge hexadezimaler Ziffern, die die Bytes der Prüfsumme darstellt.  Es muss eine gerade Anzahl hexadezimaler Ziffern sein.  Eine ungerade Ziffernanzahl löst eine Warnung zur Kompilierzeit aus, und die Direktive wird ignoriert.  
  
## Hinweise  
 Der Visual Studio\-Debugger verwendet eine Prüfsumme, um sicherzustellen, dass er immer die richtige Quelldatei findet.  Der Compiler berechnet die Prüfsumme für eine Quelldatei und gibt das Ergebnis an die Datei der PDB \(Programmdatenbank\) aus.  Der Debugger verwendet dann die PDB zum Abgleich mit der Prüfsumme, die er für die Quelldatei berechnet.  
  
 Diese Lösung funktioniert nicht bei [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)]\-Projekten, da sich die berechnete Prüfsumme auf die generierte Quelldatei und nicht auf die ASPX\-Datei bezieht.  Zur Lösung dieses Problems stellt `#pragma checksum` Prüfsummenunterstützung für [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)]\-Seiten bereit.  
  
 Wenn in [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)] ein [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)]\-Projekt erstellt wird, enthält die generierte Quelldatei eine Prüfsumme für die ASPX\-Datei, die die Quelldatei generiert hat.  Der Compiler schreibt dann diese Informationen in die PDB\-Datei.  
  
 Findet der Compiler keine `#pragma checksum`\-Direktive in der Datei, berechnet er die Prüfsumme und schreibt den Wert in die PDB\-Datei.  
  
## Beispiel  
  
```  
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{3673e4ca-6098-4ec1-890f-8fceb2a794a2}" "{012345678AB}" // New checksum  
    }  
}  
```  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Präprozessordirektiven](../../../csharp/language-reference/preprocessor-directives/index.md)