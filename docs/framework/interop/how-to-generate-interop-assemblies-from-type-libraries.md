---
title: 'Vorgehensweise: Generieren von Interopassemblys aus Typbibliotheken'
description: Generieren Sie Interopassemblys aus Typbibliotheken. Konvertieren Sie mit dem Type Library Importer-Tool (Tlbimp.exe) Co-Klassen und Schnittstellen aus einer COM-Typbibliothek in Metadaten.
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
ms.openlocfilehash: 3146d607392a590974f452e06eb5a8b125e58e69
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236363"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a>Vorgehensweise: Generieren von Interopassemblys aus Typbibliotheken

[Type Library Importer (Tlbexp.exe)](../tools/tlbimp-exe-type-library-importer.md) ist ein Befehlszeilentool, das die Co-Klassen- und Schnittstellen einer COM-Typbibliothek in Metadaten konvertiert. Dieses Tool erstellt automatisch eine Interop-Assembly und den Namespace für die Typinformationen. Nachdem die Metadaten einer Klasse verfügbar sind, können verwaltete Clients Instanzen des COM-Typs erstellen und seine Methoden aufrufen, als ob es sich um eine .NET-Instanz handeln würde. „Tlbimp.exe“ konvertiert eine ganze Typbibliothek auf einmal in Metadaten und kann keine Typinformationen für eine Teilmenge der in einer Typbibliothek definierten Typen generieren.  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a>Generieren einer Interop-Assembly aus einer Typbibliothek  
  
1. Verwenden Sie den folgenden Befehl:  
  
     **tlbimp** \<*type-library-file*>  
  
     Das Hinzufügen des **/out:** -Schalters erzeugt eine Interop-Assembly mit einem geänderten Namen, z.B. „LOANLib.dll“. Das Ändern des Namens der Interop-Assembly kann dabei helfen, sie von der ursprünglichen COM-DLL zu unterscheiden und Probleme zu verhindern, die aufgrund der doppelten Namen auftreten können.  
  
## <a name="example"></a>Beispiel  

 Der folgende Befehl erstellt die „Loanlib.dll“-Assembly im `Loanlib`-Namespace.  
  
```console  
tlbimp Loanlib.tlb  
```  
  
 Der folgende Befehl erzeugt eine Interop-Assembly mit einem geänderten Namen (LOANLib.dll).  
  
```console  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a>Siehe auch

- [Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)](importing-a-type-library-as-an-assembly.md)
- [Verfügbarmachen von COM-Komponenten für .NET Framework](exposing-com-components.md)
