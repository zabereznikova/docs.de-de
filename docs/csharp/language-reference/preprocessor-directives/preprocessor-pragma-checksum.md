---
description: '#pragma-Prüfsumme – C#-Referenz'
title: '#pragma-Prüfsumme – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: 60c491000337fd50da217e97054e86faccb2e7d7
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137980"
---
# <a name="pragma-checksum-c-reference"></a>#pragma checksum (C#-Referenz)
Erstellt für Quelldateien Prüfsummen, um beim Debuggen von ASP.NET-Seiten zu helfen.  
  
## <a name="syntax"></a>Syntax  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
## <a name="parameters"></a>Parameter  
 `"filename"`  
 Der Name der Datei, die die Überwachung von Änderungen oder Updates erfordert  
  
 `"{guid}"`  
 GUID (Globally Unique Identifier, globaler eindeutiger Bezeichner) für den Hashalgorithmus.  
  
 `"checksum_bytes"`  
 Die Zeichenfolge von hexadezimalen Ziffern, die die Bytes der Prüfsumme darstellt. Dabei muss es sich um eine gerade Anzahl hexadezimaler Ziffern handeln. Eine ungerade Anzahl von Ziffern führt zu einer Warnung zur Kompilierzeit, und die Anweisung wird ignoriert.  
  
## <a name="remarks"></a>Bemerkungen  
 Der Visual Studio-Debugger verwendet eine Prüfsumme, um sicherzustellen, dass immer die richtige Quelle gefunden wird. Der Compiler berechnet die Prüfsumme für eine Quelldatei, und speichert das Ergebnis in der Program Database-Datei (PDB). Der Debugger verwendet anschließend die PDB-Datei, um sie mit der Prüfsumme zu vergleichen, die für die Quelldatei berechnet wird.  
  
 Diese Lösung funktioniert nicht bei ASP.NET-Projekten, weil die berechnete Prüfsumme für die generierte Quelldatei und nicht für die ASPX-Datei gilt. `#pragma checksum` stellt für ASP.NET-Seiten Unterstützung von Prüfsummen bereit, um dieses Problem zu beheben.  
  
 Wenn Sie ein ASP.NET-Projekt in Visual C# erstellen, enthält die generierte Quelldatei eine Prüfsumme für die ASPX-Datei, von der die Quelle generiert wird. Der Compiler schreibt anschließend diese Informationen in die PDB-Datei.  
  
 Wenn der Compiler keine `#pragma checksum`-Direktive in der Datei findet, berechnet er die Prüfsumme und schreibt den Wert in die PDB-Datei.  
  
## <a name="example"></a>Beispiel  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Präprozessoranweisungen](./index.md)
