---
title: "Marshaling a Delegate as a Callback Method | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "data marshaling, Callback sample"
  - "marshaling, Callback sample"
ms.assetid: 6ddd7866-9804-4571-84de-83f5cc017a5a
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Marshaling a Delegate as a Callback Method
Dieses Beispiel demonstriert, wie Delegaten an eine nicht verwaltete Funktion übergeben werden, die Funktionszeiger erwartet.  Ein Delegat ist eine Klasse, die einen Verweis auf eine Methode enthalten kann und einem typsicheren Funktionszeiger oder einer Rückruffunktion entspricht.  
  
> [!NOTE]
>  Wenn Sie einen Delegaten in einem Aufruf verwenden, verhindert die Common Language Runtime für die Dauer des Aufrufs, dass für den Delegaten eine Garbage Collection durchgeführt wird.  Wenn die nicht verwaltete Funktion den Delegaten für die Verwendung nach Abschluss des Aufrufs speichert, müssen Sie die Garbage Collection manuell verhindern, bis die nicht verwaltete Funktion mit dem Delegaten beendet wird.  Weitere Informationen finden Sie im [HandleRef\-Beispiel](http://msdn.microsoft.com/de-de/ab23b04e-1d53-4ec7-b27a-e892d9298959) und im [GCHandle\-Beispiel](http://msdn.microsoft.com/de-de/6acce798-0385-4ded-a790-77da842c113f).  
  
 Das Callback\-Beispiel verwendet die folgenden nicht verwalteten Funktionen, die jeweils zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt werden:  
  
-   **TestCallBack** aus PinvokeLib.dll exportiert.  
  
    ```  
    void TestCallBack(FPTR pf, int value);  
    ```  
  
-   **TestCallBack2** aus PinvokeLib.dll exportiert.  
  
    ```  
    void TestCallBack2(FPTR2 pf2, char* value);  
    ```  
  
 [PinvokeLib.dll](http://msdn.microsoft.com/de-de/5d1438d7-9946-489d-8ede-6c694a08f614) ist eine benutzerdefinierte, nicht verwaltete Bibliothek, die eine Implementierung für die zuvor aufgelisteten Funktionen enthält.  
  
 In diesem Beispiel enthält die `LibWrap`\-Klasse verwaltete Prototypen für die Methoden `TestCallBack` und `TestCallBack2`.  Beide Methoden übergeben einen Delegaten an eine Rückruffunktion als Parameter.  Die Signatur des Delegaten muss mit der Signatur der Methode übereinstimmen, auf die er verweist.  So besitzen die Delegaten `FPtr` und `FPtr2` beispielsweise Signaturen, die mit den Methoden `DoSomething` und `DoSomething2` identisch sind.  
  
## Deklarieren von Prototypen  
 [!code-cpp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#37)]
 [!code-csharp[Conceptual.Interop.Marshaling#37](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#37)]
 [!code-vb[Conceptual.Interop.Marshaling#37](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#37)]  
  
## Aufrufen von Funktionen  
 [!code-cpp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/callback.cpp#38)]
 [!code-csharp[Conceptual.Interop.Marshaling#38](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/callback.cs#38)]
 [!code-vb[Conceptual.Interop.Marshaling#38](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/callback.vb#38)]  
  
## Siehe auch  
 [Miscellaneous Marshaling Samples](http://msdn.microsoft.com/de-de/a915c948-54e9-4d0f-a525-95a77fd8ed70)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/de-de/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)