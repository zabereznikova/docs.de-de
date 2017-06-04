---
title: "GUID_ManagedName-Attribut | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: 
  - "GUID_ManagedName"
apilocation: 
  - "alink.dll"
apitype: "COM"
f1_keywords: 
  - "GUID_ManagedName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GUID_ManagedName-Attribut"
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# GUID_ManagedName-Attribut
Definiert eine benutzerdefinierte Schnittstelle\-Attribut, das Namen des verwalteten Namespaces für eine Komponente\-Objektbibliothek Model \(COM\) angibt.  
  
## Syntax  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
#### Parameter  
 `value`  
 Der Name der verwalteten Namespace für die Bibliothek.  
  
## Definition  
 `GUID_ManagedName` wird in Cor.h wie folgt definiert:  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## Hinweise  
 Ein Attribut für die benutzerdefinierte Schnittstelle definiert die Metadaten für ein Objekt in der Typbibliothek.  
  
 Verwendung <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=fullName> oder <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=fullName> zum Abrufen der verwaltete Name des Attributs.  
  
 Weitere Informationen finden Sie unter [Interface Attributes](../Topic/Interface%20Attributes.md) in der Visual C\+\+\-Referenzdokumentation.  
  
## Beispiel  
 Das folgende Beispiel zeigt eine Bibliothek mit den `GUID_ManagedName` Attribut.  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## Anforderungen  
 **Header:** Cor.h