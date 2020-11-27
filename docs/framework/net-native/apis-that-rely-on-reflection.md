---
title: APIs, die auf Refelktion beruhen
ms.date: 03/30/2017
ms.assetid: f9532629-6594-4a41-909f-d083f30a42f3
ms.openlocfilehash: 2c361962f4570200d63037a68ef39b0c982bd5f7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251138"
---
# <a name="apis-that-rely-on-reflection"></a><span data-ttu-id="6678b-102">APIs, die auf Refelktion beruhen</span><span class="sxs-lookup"><span data-stu-id="6678b-102">APIs That Rely on Reflection</span></span>

<span data-ttu-id="6678b-103">In einigen Fällen ist die Verwendung von Reflektion im Code nicht offensichtlich, sodass die .net Native-Toolkette keine Metadaten beibehält, die zur Laufzeit benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="6678b-103">In some cases, the use of reflection in code isn't obvious, and so the .NET Native tool chain doesn't preserve metadata that is needed at run time.</span></span> <span data-ttu-id="6678b-104">In diesem Thema werden einige gängige APIs oder Programmiermuster behandelt, die nicht als Teil der Reflektions-API betrachtet werden, aber Reflektion benötigen, um erfolgreich ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="6678b-104">This topic covers some common APIs or common programming patterns that aren't considered part of the reflection API but that rely on reflection to execute successfully.</span></span> <span data-ttu-id="6678b-105">Wenn Sie diese im Quellcode verwenden, können Sie Informationen darüber in die Laufzeitanweisungsdatei (\*.rd.xml) einfügen, sodass Aufrufe dieser APIs zur Laufzeit keine [MissingMetadataException](missingmetadataexception-class-net-native.md)-Ausnahme oder sonstige Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="6678b-105">If you use them in your source code, you can add information about them to the runtime directives (.rd.xml) file so that calls to these APIs do not throw a [MissingMetadataException](missingmetadataexception-class-net-native.md) exception or some other exception at run time.</span></span>  
  
## <a name="typemakegenerictype-method"></a><span data-ttu-id="6678b-106">Type.MakeGenericType-Methode</span><span class="sxs-lookup"><span data-stu-id="6678b-106">Type.MakeGenericType method</span></span>  

 <span data-ttu-id="6678b-107">Sie können einen generischen Typ `AppClass<T>` dynamisch instanziieren, indem Sie die <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType>-Methode aufrufen. Dazu verwenden Sie Code wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="6678b-107">You can dynamically instantiate a generic type `AppClass<T>` by calling the <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method by using code like this:</span></span>  
  
 [!code-csharp[ProjectN#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/type_makegenerictype1.cs#1)]  
  
 <span data-ttu-id="6678b-108">Damit dieser Code zur Laufzeit erfolgreich ist, sind mehrere Elemente von Metadaten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6678b-108">For this code to succeed at run time, several items of metadata are required.</span></span> <span data-ttu-id="6678b-109">Das erste sind `Browse`-Metadaten für den nicht instanziierten generischen Typ `AppClass<T>`:</span><span class="sxs-lookup"><span data-stu-id="6678b-109">The first is `Browse` metadata for the uninstantiated generic type, `AppClass<T>`:</span></span>  
  
```xml  
<Type Name="App1.AppClass`1" Browse="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="6678b-110">Auf diese Weise kann der Aufruf der <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>-Methode erfolgreich sein und ein gültiges <xref:System.Type>-Objekt zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6678b-110">This allows the <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> method call to succeed and return a valid <xref:System.Type> object.</span></span>  
  
 <span data-ttu-id="6678b-111">Aber auch wenn Sie Metadaten für den nicht instanziierten generischen Typ hinzufügen, löst der Aufruf der <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType>-Methode eine [MissingMetadataException](missingmetadataexception-class-net-native.md)-Ausnahme aus:</span><span class="sxs-lookup"><span data-stu-id="6678b-111">But even when you add metadata for the uninstantiated generic type, calling the <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method throws a [MissingMetadataException](missingmetadataexception-class-net-native.md) exception:</span></span>  
  
<span data-ttu-id="6678b-112">Dieser Vorgang kann nicht ausgeführt werden, weil Metadaten für den folgenden Typ aus Leistungsgründen entfernt wurden:</span><span class="sxs-lookup"><span data-stu-id="6678b-112">This operation cannot be carried out as metadata for the following type was removed for performance reasons:</span></span>  
  
<span data-ttu-id="6678b-113">`App1.AppClass`1<System. Int32>'.</span><span class="sxs-lookup"><span data-stu-id="6678b-113">`App1.AppClass`1<System.Int32>\`.</span></span>  
  
 <span data-ttu-id="6678b-114">Sie können der Laufzeitdirektivendatei die folgende Laufzeitdirektive hinzufügen, um `Activate`-Metadaten für die spezifische Instanziierung über `AppClass<T>` von <xref:System.Int32?displayProperty=nameWithType> hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="6678b-114">You can add the following run-time directive to the runtime directives file to add `Activate` metadata for the specific instantiation over `AppClass<T>` of <xref:System.Int32?displayProperty=nameWithType>:</span></span>  
  
```xml  
<TypeInstantiation Name="App1.AppClass" Arguments="System.Int32"
                   Activate="Required Public" />  
```  
  
 <span data-ttu-id="6678b-115">Jede andere Instanziierung über `AppClass<T>` erfordert eine separate Anweisung, wenn sie mit der <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType>-Methode erstellt und nicht statisch verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6678b-115">Each different instantiation over `AppClass<T>` requires a separate directive if it is being created with the <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method and not used statically.</span></span>  
  
## <a name="methodinfomakegenericmethod-method"></a><span data-ttu-id="6678b-116">MethodInfo.MakeGenericMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="6678b-116">MethodInfo.MakeGenericMethod method</span></span>  

 <span data-ttu-id="6678b-117">In einer Klasse `Class1` mit einer generischen Methode `GetMethod<T>(T t)` kann `GetMethod` durch Reflektion mithilfe von Code wie dem folgenden aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="6678b-117">Given a class `Class1` with a generic method `GetMethod<T>(T t)`, `GetMethod` can be invoked through reflection by using code like this:</span></span>  
  
 [!code-csharp[ProjectN#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/makegenericmethod1.cs#2)]  
  
 <span data-ttu-id="6678b-118">Damit dieser Code erfolgreich ausgeführt wird, sind mehrere Elemente von Metadaten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="6678b-118">To run successfully, this code requires several items of metadata:</span></span>  
  
- <span data-ttu-id="6678b-119">`Browse`-Metadaten für den Typ, dessen Methode Sie aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="6678b-119">`Browse` metadata for the type whose method you want to call.</span></span>  
  
- <span data-ttu-id="6678b-120">`Browse`-Metadaten für die Methode, die Sie aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="6678b-120">`Browse` metadata for the method you want to call.</span></span>  <span data-ttu-id="6678b-121">Ist es eine öffentliche Methode, umfasst das Hinzufügen von öffentlichen `Browse`-Metadaten für den enthaltenden Typ auch die Methode.</span><span class="sxs-lookup"><span data-stu-id="6678b-121">If it is a public method, adding public `Browse` metadata for the containing type includes the method, too.</span></span>  
  
- <span data-ttu-id="6678b-122">Dynamische Metadaten für die Methode, die Sie aufrufen möchten, damit der Reflektionsaufruf-Delegat nicht von der .net Native-Toolkette entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="6678b-122">Dynamic metadata for the method you want to call, so that the reflection invocation delegate is not removed by the .NET Native tool chain.</span></span> <span data-ttu-id="6678b-123">Wenn dynamische Metadaten für die Methode fehlen, wird beim Aufruf der <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType>-Methode die folgende Ausnahme ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="6678b-123">If dynamic metadata is missing for the method, the following exception is thrown when the <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> method is called:</span></span>  
  
    ```output
    MakeGenericMethod() cannot create this generic method instantiation because the instantiation was not metadata-enabled: 'App1.Class1.GenMethod<Int32>(Int32)'.  
    ```  
  
 <span data-ttu-id="6678b-124">Die folgenden Laufzeitanweisungen stellen sicher, dass alle erforderlichen Metadaten verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="6678b-124">The following runtime directives ensure that all required metadata is available:</span></span>  
  
```xml  
<Type Name="App1.Class1" Browse="Required PublicAndInternal">  
   <MethodInstantiation Name="GenMethod" Arguments="System.Int32" Dynamic="Required"/>  
</Type>  
```  
  
 <span data-ttu-id="6678b-125">Für jede unterschiedliche Instanziierung der Methode, die dynamisch aufgerufen wird, ist eine `MethodInstantiation`-Direktive erforderlich, und das `Arguments`-Element wird jedem unterschiedlichen Instanziierungsargument entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6678b-125">A `MethodInstantiation` directive is required for each different instantiation of the method that is dynamically invoked, and the `Arguments` element is updated to reflect each different instantiation argument.</span></span>  
  
## <a name="arraycreateinstance-and-typemaketypearray-methods"></a><span data-ttu-id="6678b-126">Methoden Array.CreateInstance und Type.MakeTypeArray</span><span class="sxs-lookup"><span data-stu-id="6678b-126">Array.CreateInstance and Type.MakeTypeArray methods</span></span>  

 <span data-ttu-id="6678b-127">Das folgende Beispiel ruft die Methoden <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> und <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> für einen Typ `Class1` auf.</span><span class="sxs-lookup"><span data-stu-id="6678b-127">The following example calls the <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> methods on a type, `Class1`.</span></span>  
  
 [!code-csharp[ProjectN#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/array1.cs#3)]  
  
 <span data-ttu-id="6678b-128">Wenn keine Array-Metadaten vorhanden sind, führt dies zu folgender Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="6678b-128">If no array metadata is present, the following error results:</span></span>  
  
```output
This operation cannot be carried out as metadata for the following type was removed for performance reasons:  
  
App1.Class1[]  
  
Unfortunately, no further information is available.  
```  
  
 <span data-ttu-id="6678b-129">`Browse`-Metadaten für den Arraytyp sind erforderlich, um ihn dynamisch zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="6678b-129">`Browse` metadata for the array type is required to dynamically instantiate it.</span></span>  <span data-ttu-id="6678b-130">Die folgende Laufzeitdirektive ermöglicht die dynamische Instanziierung von `Class1[]`.</span><span class="sxs-lookup"><span data-stu-id="6678b-130">The following runtime directive allows dynamic instantiation of `Class1[]`.</span></span>  
  
```xml  
<Type Name="App1.Class1[]" Browse="Required Public" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="6678b-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6678b-131">See also</span></span>

- [<span data-ttu-id="6678b-132">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="6678b-132">Getting Started</span></span>](getting-started-with-net-native.md)
- [<span data-ttu-id="6678b-133">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="6678b-133">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
