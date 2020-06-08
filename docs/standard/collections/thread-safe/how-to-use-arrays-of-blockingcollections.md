---
title: 'Gewusst wie: Verwenden von Arrays mit blockierenden Sammlungen in einer Pipeline'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
ms.openlocfilehash: 2309676435a6603aaa9bbbd95953c0179b908622
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287830"
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a>Gewusst wie: Verwenden von Arrays mit blockierenden Sammlungen in einer Pipeline
Das folgende Beispiel zeigt die Verwendung von <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>-Objektarrays mit statischen Methoden wie <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> und <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>, um eine schnelle und flexible Datenübertragung zwischen Komponenten zu implementieren.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht eine grundlegende Pipeline-Implementierung, in der alle Objekte gleichzeitig Daten aus der Eingabeauflistung entnehmen, sie transformieren und dann an die Ausgabeauflistung übergeben.  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Concurrent?displayProperty=nameWithType>
- [Threadsichere Sammlungen](index.md)
