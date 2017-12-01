---
title: "Gewusst wie: Auflisten von Speichern für isolierten Speicher"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enumerating stores
- data storage using isolated storage, enumerating stores
- storing data using isolated storage, enumerating stores
- stores, enumerating
- isolated storage, enumerating stores
- data stores, enumerating
ms.assetid: 0fcf279a-f241-48f0-8034-2e3d331f1fcb
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f8863f1d8b3c7f4ed8f65f8f8eb3e8af51b0405
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-stores-for-isolated-storage"></a>Gewusst wie: Auflisten von Speichern für isolierten Speicher
Sie können alle isolierten Speicher für den aktuellen Benutzer auflisten, mit der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A?displayProperty=nameWithType> statische Methode. Diese Methode nimmt ein <xref:System.IO.IsolatedStorage.IsolatedStorageScope> Wert und gibt eine <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Enumerator. Zum Auflisten von speichern, benötigen Sie die <xref:System.Security.Permissions.IsolatedStorageFilePermission> Berechtigung, der angibt, die <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> Wert. Beim Aufrufen der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> Methode mit dem <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> Wert, es gibt ein Array von <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Objekte, die für den aktuellen Benutzer definiert sind.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird erhält einen Speicher, der nach Benutzer und Assembly isoliert ist, erstellt einige Dateien und ruft diese Dateien ab, indem die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetEnumerator%2A> Methode.  
  
 [!code-csharp[Conceptual.IsolatedStorage#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source2.cs#2)]
 [!code-vb[Conceptual.IsolatedStorage#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [Isolierter Speicher](../../../docs/standard/io/isolated-storage.md)
