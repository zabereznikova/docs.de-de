---
title: Lokale Methodenaufrufe
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d652072d5f2e0e0cfc74d627b573389864bca9dc
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="local-method-calls"></a><span data-ttu-id="57ec7-102">Lokale Methodenaufrufe</span><span class="sxs-lookup"><span data-stu-id="57ec7-102">Local Method Calls</span></span>
<span data-ttu-id="57ec7-103">Ein Aufruf einer lokalen Methode wird innerhalb des Objektmodells ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="57ec7-103">A local method call is one that is executed within the object model.</span></span> <span data-ttu-id="57ec7-104">Ein Remotemethodenaufruf wird von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in SQL übersetzt und zur Ausführung an das Datenbankmodul übergeben.</span><span class="sxs-lookup"><span data-stu-id="57ec7-104">A remote method call is one that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates to SQL and transmits to the database engine for execution.</span></span> <span data-ttu-id="57ec7-105">Lokale Methodenaufrufe sind erforderlich, wenn [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht den Aufruf in SQL übersetzen.</span><span class="sxs-lookup"><span data-stu-id="57ec7-105">Local method calls are needed when [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] cannot translate the call into SQL.</span></span> <span data-ttu-id="57ec7-106">Andernfalls ein <xref:System.InvalidOperationException> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="57ec7-106">Otherwise, an <xref:System.InvalidOperationException> is thrown.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="57ec7-107">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="57ec7-107">Example 1</span></span>  
 <span data-ttu-id="57ec7-108">Im folgenden Beispiel wird veranschaulicht, wie eine `Order`-Klasse der Tabelle Bestellungen in der Datenbank Northwind zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="57ec7-108">In the following example, an `Order` class is mapped to the Orders table in the Northwind sample database.</span></span> <span data-ttu-id="57ec7-109">Eine lokale Instanzmethode wurde der Klasse hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="57ec7-109">A local instance method has been added to the class.</span></span>  
  
 <span data-ttu-id="57ec7-110">In Abfrage 1 wird der Konstruktor für die `Order`-Klasse lokal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="57ec7-110">In Query 1, the constructor for the `Order` class is executed locally.</span></span> <span data-ttu-id="57ec7-111">Hat [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in Abfrage 2 versucht, `LocalInstanceMethod()` in SQL zu übersetzen, würde der Versuch fehlschlagen, und eine <xref:System.InvalidOperationException>-Ausnahme würde ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="57ec7-111">In Query 2, if [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tried to translate `LocalInstanceMethod()`into SQL, the attempt would fail and an <xref:System.InvalidOperationException> exception would be thrown.</span></span> <span data-ttu-id="57ec7-112">Aber da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Aufrufe einer lokalen Methode unterstützt, löst Abfrage 2 keine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="57ec7-112">But because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides support for local method calls, Query2 will not throw an exception.</span></span>  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="57ec7-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57ec7-113">See Also</span></span>  
 [<span data-ttu-id="57ec7-114">Hintergrundinformationen</span><span class="sxs-lookup"><span data-stu-id="57ec7-114">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
