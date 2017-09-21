---
title: 'Gewusst wie: Generieren von Interop-Assemblys aus Typbibliotheken'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ff406fb14a21b0425444d04e98bbaca127d3687b
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a>Gewusst wie: Generieren von Interop-Assemblys aus Typbibliotheken
[Type Library Importer (Tlbexp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) ist ein Befehlszeilentool, das die Co-Klassen- und Schnittstellen einer COM-Typbibliothek in Metadaten konvertiert. Dieses Tool erstellt automatisch eine Interop-Assembly und den Namespace für die Typinformationen. Nachdem die Metadaten einer Klasse verfügbar sind, können verwaltete Clients Instanzen des COM-Typs erstellen und seine Methoden aufrufen, als ob es sich um eine .NET-Instanz handeln würde. „Tlbimp.exe“ konvertiert eine ganze Typbibliothek auf einmal in Metadaten und kann keine Typinformationen für eine Teilmenge der in einer Typbibliothek definierten Typen generieren.  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a>Generieren einer Interop-Assembly aus einer Typbibliothek  
  
1.  Verwenden Sie den folgenden Befehl:  
  
     **tlbimp** \<*type-library-file*>  
  
     Das Hinzufügen des **/out:**-Schalters erzeugt eine Interop-Assembly mit einem geänderten Namen, z.B. „LOANLib.dll“. Das Ändern des Namens der Interop-Assembly kann dabei helfen, sie von der ursprünglichen COM-DLL zu unterscheiden und Probleme zu verhindern, die aufgrund der doppelten Namen auftreten können.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl erstellt die „Loanlib.dll“-Assembly im `Loanlib`-Namespace.  
  
```  
tlbimp Loanlib.dll  
```  
  
 Der folgende Befehl erzeugt eine Interop-Assembly mit einem geänderten Namen (LOANLib.dll).  
  
```  
tlbimp LoanLib.dll /out: LOANLib.dll  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Importieren einer Typbibliothek als Assembly](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)   
 [Verfügbarmachen von COM-Komponenten für .NET Framework](../../../docs/framework/interop/exposing-com-components.md)

