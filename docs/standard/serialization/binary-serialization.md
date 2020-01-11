---
title: Binäre Serialisierung
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 9df9b73a1a1347b952d76b76c9058578f5e9f401
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901052"
---
# <a name="binary-serialization"></a><span data-ttu-id="b5a01-102">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="b5a01-102">Binary serialization</span></span>

<span data-ttu-id="b5a01-103">Die Serialisierung kann als Prozess der Speicherung eines Objektzustands in einem Speichermedium definiert werden.</span><span class="sxs-lookup"><span data-stu-id="b5a01-103">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="b5a01-104">Im Rahmen dieses Vorgangs werden die öffentlichen und privaten Felder des Objekts und der Name der Klasse, einschließlich der Assembly, die die Klasse enthält, in einen Bytestream umgewandelt, der dann in einen Datenstream geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="b5a01-104">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="b5a01-105">Wenn das Objekt anschließend deserialisiert wird, wird ein genauer Klon des ursprünglichen Objekts erstellt.</span><span class="sxs-lookup"><span data-stu-id="b5a01-105">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="b5a01-106">Bei der Implementierung eines Serialisierungsmechanismus in einer objektorientierten Umgebung muss vielfach zwischen einfacher Handhabung und Flexibilät abgewogen werden.</span><span class="sxs-lookup"><span data-stu-id="b5a01-106">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="b5a01-107">Dieser Vorgang lässt sich größtenteils automatisieren, sofern Sie ausreichend Kontrolle über den Vorgang haben.</span><span class="sxs-lookup"><span data-stu-id="b5a01-107">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="b5a01-108">Es kann beispielsweise Situationen geben, in denen eine einfache binäre Serialisierung nicht ausreichend ist, oder aus einem bestimmt Grund kann es erforderlich sein zu entscheiden, welche Felder einer Klasse serialisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b5a01-108">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="b5a01-109">In den folgenden Abschnitten wird der robuste Serialisierungsmechanismus untersucht, der von .NET bereitgestellt wird, und es werden einige wichtige Funktionen hervorgehoben, mit denen Sie diesen Vorgang an Ihre Anforderungen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="b5a01-109">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="b5a01-110">Der Zustand eines UTF-8- oder UTF-7-codierten Objektes wird nicht beibehalten, wenn das Objekt mit verschiedenen Versionen von .NET Framework serialisiert und deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b5a01-110">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="b5a01-111">Die binäre Serialisierung ermöglicht das ändern privater Member innerhalb eines Objekts und somit die Änderung des Zustands.</span><span class="sxs-lookup"><span data-stu-id="b5a01-111">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="b5a01-112">Aus diesem Grund werden andere serialisierungsframe Works wie <xref:System.Text.Json?displayProperty=fullName>empfohlen, die auf der öffentlichen API-Oberfläche funktionieren.</span><span class="sxs-lookup"><span data-stu-id="b5a01-112">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="b5a01-113">.NET Core</span><span class="sxs-lookup"><span data-stu-id="b5a01-113">.NET Core</span></span>

<span data-ttu-id="b5a01-114">.Net Core unterstützt die binäre Serialisierung für eine Teilmenge von Typen.</span><span class="sxs-lookup"><span data-stu-id="b5a01-114">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="b5a01-115">Die Liste der unterstützten Typen finden Sie im nachfolgenden Abschnitt zu [serialisierbaren Typen](#serializable-types) .</span><span class="sxs-lookup"><span data-stu-id="b5a01-115">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="b5a01-116">Die aufgelisteten Typen sind garantiert serialisierbar zwischen .NET Framework 4.5.1 und höheren Versionen und zwischen .net Core 2,0 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="b5a01-116">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="b5a01-117">Andere .net-Implementierungen, wie z. b. Mono, werden nicht offiziell unterstützt, sollten aber auch funktionieren.</span><span class="sxs-lookup"><span data-stu-id="b5a01-117">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="b5a01-118">Serialisierbare Typen</span><span class="sxs-lookup"><span data-stu-id="b5a01-118">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="b5a01-119">Typ</span><span class="sxs-lookup"><span data-stu-id="b5a01-119">Type</span></span> | <span data-ttu-id="b5a01-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5a01-120">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-121">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-121">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-122">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-122">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-123">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-124">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-125">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-126">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-127">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-128">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-129">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-130">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-131">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-132">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-133">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-134">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Hashtable?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Queue?displayProperty=nameWithType> | |
> | <xref:System.Collections.SortedList?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Stack?displayProperty=nameWithType> | |
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="b5a01-135">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-136">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-136">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-137">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-138">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-139">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-140">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-140">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="b5a01-141">Die Serialisierung von .NET Framework zu .net Core wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b5a01-141">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-142">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-142">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="b5a01-143">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-143">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-144">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-145">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-146">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-147">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-148">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-149">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-150">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="b5a01-151">Ab .net Core 2.0.2 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="b5a01-151">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-152">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-153">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-153">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-154">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-155">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="b5a01-156">Wenn Sie `RemotingFormat` auf `SerializationFormat.Binary`festlegen, kann es nur mit .net Core 2,1 und höheren Versionen ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="b5a01-156">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-157">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-158">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-158">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-159">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-160">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-161">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-162">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-163">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-164">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-165">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-166">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-167">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-168">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-169">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-169">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="b5a01-170">Die Serialisierung von .NET Framework zu .net Core wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b5a01-170">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-171">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-171">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-172">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-172">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-173">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-174">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-175">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-176">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-177">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-178">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-179">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="b5a01-180">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-181">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-182">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-183">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-184">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-185">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-186">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-187">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-188">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-189">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-190">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-191">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-192">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-193">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-194">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-195">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-196">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-197">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-198">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-199">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-200">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-201">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-202">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-203">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-204">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-205">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="b5a01-206">Ab .net Core 2.0.6.</span><span class="sxs-lookup"><span data-stu-id="b5a01-206">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-207">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-208">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-208">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-209">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-210">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="b5a01-211">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-212">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-213">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-214">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-215">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-216">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-217">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-218">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-219">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-220">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-221">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-222">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-223">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-224">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-225">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-226">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-227">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-228">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-229">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-230">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-231">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-232">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-233">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-234">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-235">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-236">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-237">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-238">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-239">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-240">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-241">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-242">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-243">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-244">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-245">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-246">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-247">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-248">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-249">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-250">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-251">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-252">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-253">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-254">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-255">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-256">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-257">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-258">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-259">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-259">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="b5a01-260">Die Serialisierung von .NET Framework zu .net Core wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b5a01-260">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-261">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-261">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-262">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-262">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-263">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-264">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-265">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-266">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-267">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-268">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-269">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-270">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-271">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-272">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-273">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-274">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-275">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-276">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-277">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-278">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-279">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-280">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-281">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-281">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="b5a01-282">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-283">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-283">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-284">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-285">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-286">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-286">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="b5a01-287">Eingeschränkte Serialisierungsdaten.</span><span class="sxs-lookup"><span data-stu-id="b5a01-287">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-288">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-288">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-289">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-289">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-290">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-291">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-292">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-293">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-294">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-295">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-296">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-297">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-298">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-299">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-300">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-301">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-302">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-303">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-304">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-305">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-306">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-307">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-308">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-309">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-310">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-311">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-312">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-313">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-314">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-315">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-316">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-317">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-318">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-319">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-320">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="b5a01-321">Nicht serialisierbar in .NET Framework 4,7 und früheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="b5a01-321">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-322">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-323">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-323">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-324">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-325">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-326">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-327">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="b5a01-328">Ab .net Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="b5a01-328">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="b5a01-329">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5a01-329">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="b5a01-330">Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="b5a01-330">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="b5a01-331">[XML and SOAP Serialization (XML- und SOAP-Serialisierung)](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="b5a01-331">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="b5a01-332">Beschreibt den XML-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b5a01-332">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="b5a01-333">[Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="b5a01-333">[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="b5a01-334">Beschreibt Richtlinien für das Schreiben sicheren Codes, die beim Schreiben von befolgt werden sollten, der Serialisierungen durchführt.</span><span class="sxs-lookup"><span data-stu-id="b5a01-334">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="b5a01-335">[.NET-Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)) -</span><span class="sxs-lookup"><span data-stu-id="b5a01-335">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="b5a01-336">Beschreibt die verschiedenen Methoden, die in .NET Framework für die Remote Kommunikation beginnen.</span><span class="sxs-lookup"><span data-stu-id="b5a01-336">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="b5a01-337">[Mit ASP.net-und XML-Webdienst Clients erstellte XML-Webdienste](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b5a01-337">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="b5a01-338">Artikel, die beschreiben und erläutern, wie Sie mit ASP.NET erstellte XML-Webdienste programmieren.</span><span class="sxs-lookup"><span data-stu-id="b5a01-338">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
