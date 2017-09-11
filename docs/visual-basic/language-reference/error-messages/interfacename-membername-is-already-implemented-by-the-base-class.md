---
title: '&quot;&lt;%InterfaceName&gt;.&lt; Membername&gt;&quot;ist bereits implementiert die Basisklasse&quot;&lt;Baseclassname&gt;&quot;. Die erneute Implementierung von &lt;Typ&gt; davon ausgegangen, dass | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42015
- bc42015
dev_langs:
- VB
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d792485f13e2b675858d82aa7219670a17fd974e
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a><span data-ttu-id="5b613-103">'&lt;%InterfaceName&gt;.&lt; Membername&gt;"ist bereits implementiert die Basisklasse"&lt;Baseclassname&gt;".</span><span class="sxs-lookup"><span data-stu-id="5b613-103">&#39;&lt;interfacename&gt;.&lt;membername&gt;&#39; is already implemented by the base class &#39;&lt;baseclassname&gt;&#39;.</span></span> <span data-ttu-id="5b613-104">Die erneute Implementierung von &lt;Typ&gt; davon ausgegangen, dass</span><span class="sxs-lookup"><span data-stu-id="5b613-104">Re-implementation of &lt;type&gt; assumed</span></span>
<span data-ttu-id="5b613-105">Eine Eigenschaft, eine Prozedur oder ein Ereignis in einer abgeleiteten Klasse verwendet eine `Implements` -Klausel für einen Schnittstellenmember, der bereits in der Basisklasse implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="5b613-105">A property, procedure, or event in a derived class uses an `Implements` clause specifying an interface member that is already implemented in the base class.</span></span>  
  
 <span data-ttu-id="5b613-106">Ein Schnittstellenmember, der von seiner Basisklasse implementiert wird, kann von einer abgeleiteten Klasse erneut implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="5b613-106">A derived class can reimplement an interface member that is implemented by its base class.</span></span> <span data-ttu-id="5b613-107">Dieser Vorgang ist nicht identisch mit dem Überschreiben der Basisklassenimplementierung.</span><span class="sxs-lookup"><span data-stu-id="5b613-107">This is not the same as overriding the base class implementation.</span></span> <span data-ttu-id="5b613-108">Weitere Informationen finden Sie unter [implementiert](../../../visual-basic/language-reference/statements/implements-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5b613-108">For more information, see [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).</span></span>  
  
 <span data-ttu-id="5b613-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="5b613-109">By default, this message is a warning.</span></span> <span data-ttu-id="5b613-110">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="5b613-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="5b613-111">**Fehler-ID:** BC42015</span><span class="sxs-lookup"><span data-stu-id="5b613-111">**Error ID:** BC42015</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5b613-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="5b613-112">To correct this error</span></span>  
  
-   <span data-ttu-id="5b613-113">Wenn Sie beabsichtigen, den Schnittstellenmember erneut zu implementieren, müssen Sie keine Maßnahme ergreifen.</span><span class="sxs-lookup"><span data-stu-id="5b613-113">If you intend to reimplement the interface member, you do not need to take any action.</span></span> <span data-ttu-id="5b613-114">Code in der abgeleiteten Klasse greift auf die reimplemented Member, es sei denn, Sie verwenden die `MyBase` -Schlüsselwort verwenden, um die Implementierung der Basisklasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5b613-114">Code in your derived class accesses the reimplemented member unless you use the `MyBase` keyword to access the base class implementation.</span></span>  
  
-   <span data-ttu-id="5b613-115">Wenn Sie keine erneute Implementierung des Schnittstellenmembers beabsichtigen, entfernen Sie die `Implements` -Klausel aus der Deklaration der Eigenschaft, Prozedur oder des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="5b613-115">If you do not intend to reimplement the interface member, remove the `Implements` clause from the property, procedure, or event declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b613-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b613-116">See Also</span></span>  
 [<span data-ttu-id="5b613-117">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5b613-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
