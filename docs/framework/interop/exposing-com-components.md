---
title: Verfügbarmachen von COM-Komponenten für .NET Framework
description: Lernen Sie den Prozess des Verfügbarmachens von COM-Komponenten für .NET kennen. COM-Komponenten sind in verwaltetem Code als Geschäftsanwendungen mittlerer Ebene oder isolierte Funktionalität nützlich.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
ms.openlocfilehash: 4e18e3f49dacbb3a358aa7e9785a5dda93206164
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267064"
---
# <a name="exposing-com-components-to-the-net-framework"></a>Verfügbarmachen von COM-Komponenten für .NET Framework

In diesem Abschnitt wird der Prozess zusammengefasst, der benötigt wird, um eine vorhandene COM-Komponente für verwalteten Code verfügbar zu machen. Details zum Schreiben von COM-Servern, die eng in .NET Framework eingebunden sind, finden Sie unter [Entwurfsüberlegungen für die Interoperation](/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).
  
 Vorhandene COM-Komponenten sind wertvolle Ressourcen in verwaltetem Code als Geschäftsanwendungen mittlerer Ebene oder als isolierte Funktion. Eine ideale Komponente verfügt über eine primäre Interop-Assembly, und entspricht weitgehend den Programmierstandards von COM.  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a>Verfügbarmachen von COM-Komponenten für .NET Framework  
  
1. [Import a type library as an assembly (Importieren einer Typbibliothek als Assembly)](importing-a-type-library-as-an-assembly.md).  
  
     Die Common Language Runtime erfordert Metadaten für alle Typen, einschließlich COM-Typen. Es gibt mehrere Möglichkeiten zum Abrufen einer Assembly mit COM-Typen, die als Metadaten importiert werden.  
  
2. [Use COM types in managed Code](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)) (Verwenden von COM-Typen in verwaltetem Code).  
  
     Sie können für das COM-Objekt auf die gleiche Weise COM-Typen überprüfen, Instanzen aktivieren und Methoden aufrufen, wie für einen verwalteten Typ.  
  
3. [Kompilieren Sie ein Interop-Projekt](compiling-an-interop-project.md).  
  
     Das Windows SDK bietet Compiler für verschiedene mit der Common Language Specification (CLS) kompatible Sprachen an, einschließlich Visual Basic, C# und C++.  
  
4. [Geben Sie eine Interop-Anwendung weiter](deploying-an-interop-application.md).  
  
     Interop-Anwendungen werden am besten als signierte Assemblys [mit starkem Namen](../../standard/assembly/strong-named.md) im globalen Assemblycache bereitgestellt.  
  
## <a name="see-also"></a>Siehe auch

- [Interoperabilität mit nicht verwaltetem Code](index.md)
- [Entwurfsüberlegungen für die Interoperation](/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))
- [COM-Interop-Beispiel: .NET-Client und COM-Server](com-interop-sample-net-client-and-com-server.md)
- [Sprachunabhängigkeit und sprachunabhängige Komponenten](../../standard/language-independence-and-language-independent-components.md)
- [Gacutil.exe (Global Assembly Cache-Tool)](../tools/gacutil-exe-gac-tool.md)
