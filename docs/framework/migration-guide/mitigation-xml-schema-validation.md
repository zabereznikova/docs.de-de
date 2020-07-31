---
title: 'Entschärfung: XML-Schema-Validierung'
description: Die XSD-Schemavalidierung erkennt Verstöße gegen die „unique“-Einschränkung, wenn ein Verbundschlüssel verwendet wird und ein Schlüssel in .NET Framework 4.6 leer ist.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
ms.openlocfilehash: 0672361ca5c0bc7cb6ec166f59278b93555e0947
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475306"
---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="4cee0-103">Entschärfung: XML-Schemavalidierung</span><span class="sxs-lookup"><span data-stu-id="4cee0-103">Mitigation: XML Schema Validation</span></span>
<span data-ttu-id="4cee0-104">In .NET Framework 4.6 erkennt die XSD-Schemavalidierung Verstöße gegen die Unique-Einschränkung, wenn ein Verbundschlüssel verwendet wird und ein Schlüssel leer ist.</span><span class="sxs-lookup"><span data-stu-id="4cee0-104">In the .NET Framework 4.6, XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="4cee0-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="4cee0-105">Impact</span></span>  
 <span data-ttu-id="4cee0-106">Die Auswirkung dieser Änderung sollte minimal sein: In Abhängigkeit der Schemaspezifikation wir ein Schemavalidierungsfehler erwartet, wenn `xsd:unique` mithilfe eines Verbundschlüssels mit einem leeren Schlüssel verletzt wird.</span><span class="sxs-lookup"><span data-stu-id="4cee0-106">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="4cee0-107">Minderung</span><span class="sxs-lookup"><span data-stu-id="4cee0-107">Mitigation</span></span>  
 <span data-ttu-id="4cee0-108">Ob ein Schemavalidierungsfehler erkannt wird, wenn ein Verbundschlüssel über einen leeren Schlüssel verfügt, kann konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="4cee0-108">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
- <span data-ttu-id="4cee0-109">Bei Apps, die auf .NET Framework 4.6 ausgerichtet sind, ist die Erkennung des Schemavalidierungsfehlers standardmäßig aktiviert. Es ist jedoch möglich, dieses Verhalten zu deaktivieren, sodass der Schemavalidierungsfehler nicht erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="4cee0-109">Starting with the apps that target the .NET Framework 4.6, detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
- <span data-ttu-id="4cee0-110">In Apps, die unter .NET Framework 4.6 ausgeführt werden, aber auf .NET Framework 4.5.2 und frühere Versionen ausgerichtet sind, wird standardmäßig kein Schemavalidierungsfehler erkannt. Es ist jedoch möglich, dieses Verhalten zu aktivieren, sodass der Schemavalidierungsfehler erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="4cee0-110">In apps that run under the .NET Framework 4.6 but target the .NET Framework 4.5.2 and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="4cee0-111">Dieses Verhalten kann mithilfe der Klasse <xref:System.AppContext> konfiguriert werden, um den Wert des Switches `System.Xml.IgnoreEmptyKeySequences` zu definieren.</span><span class="sxs-lookup"><span data-stu-id="4cee0-111">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="4cee0-112">Da der Standardwert des Switches `false` (leere Schlüsselsequenzen werden nicht ignoriert) lautet, können auf .NET Framework 4.6 ausgerichtete Apps dieses Verhalten deaktivieren, indem der Wert des Switches mithilfe des folgenden Codes auf `true` festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="4cee0-112">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the .NET Framework 4.6 can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 <span data-ttu-id="4cee0-113">Da der Standardwert des Switches bei Apps, die auf .NET Framework 4.5.2 und frühere Versionen ausgerichtet sind, `true` (leere Schlüsselsequenzen werden ignoriert) lautet, kann sichergestellt werden, dass ein Verbundschlüssel mit einem leeren Schlüssel einen Schemavalidierungsfehler generiert, indem der Wert des Switches mithilfe des folgenden Codes auf `false` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="4cee0-113">For apps that target the .NET Framework 4.5.2 and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="4cee0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cee0-114">See also</span></span>

- [<span data-ttu-id="4cee0-115">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="4cee0-115">Application compatibility</span></span>](application-compatibility.md)
