---
title: ISymUnmanagedDocument::GetCheckSumAlgorithmId-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSumAlgorithmId
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSumAlgorithmId method [.NET Framework debugging]
- GetCheckSumAlgorithmId method [.NET Framework debugging]
ms.assetid: c7f941cd-e25b-4b85-b1ce-5f77c9208fa9
topic_type:
- apiref
ms.openlocfilehash: 3c82cf45bca3cc9ec73255586db73a903edaf1ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698571"
---
# <a name="isymunmanageddocumentgetchecksumalgorithmid-method"></a><span data-ttu-id="b7b53-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId-Methode</span><span class="sxs-lookup"><span data-stu-id="b7b53-102">ISymUnmanagedDocument::GetCheckSumAlgorithmId Method</span></span>

<span data-ttu-id="b7b53-103">Ruft den Prüfsummen Algorithmus-Bezeichner ab oder gibt eine GUID aller Nullen zurück, wenn keine Prüfsumme vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b7b53-103">Gets the checksum algorithm identifier, or returns a GUID of all zeros if there is no checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7b53-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7b53-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSumAlgorithmId(  
    [out, retval] GUID*  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7b53-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7b53-105">Parameters</span></span>  

 `pRetVal`  
 <span data-ttu-id="b7b53-106">vorgenommen Ein Zeiger auf eine Variable, die den Prüfsummen Algorithmus-Bezeichner empfängt.</span><span class="sxs-lookup"><span data-stu-id="b7b53-106">[out] A pointer to a variable that receives the checksum algorithm identifier.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7b53-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b7b53-107">Return Value</span></span>  

 <span data-ttu-id="b7b53-108">S_OK, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="b7b53-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7b53-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7b53-109">See also</span></span>

- [<span data-ttu-id="b7b53-110">ISymUnmanagedDocument-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b7b53-110">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)
