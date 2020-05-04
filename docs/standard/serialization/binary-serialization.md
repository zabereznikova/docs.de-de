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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401268"
---
# <a name="binary-serialization"></a><span data-ttu-id="41e2f-102">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="41e2f-102">Binary serialization</span></span>

<span data-ttu-id="41e2f-103">Die Serialisierung kann als Prozess der Speicherung eines Objektzustands in einem Speichermedium definiert werden.</span><span class="sxs-lookup"><span data-stu-id="41e2f-103">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="41e2f-104">Im Rahmen dieses Vorgangs werden die öffentlichen und privaten Felder des Objekts und der Name der Klasse, einschließlich der Assembly, die die Klasse enthält, in einen Bytestream umgewandelt, der dann in einen Datenstream geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="41e2f-104">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="41e2f-105">Wenn das Objekt anschließend deserialisiert wird, wird ein genauer Klon des ursprünglichen Objekts erstellt.</span><span class="sxs-lookup"><span data-stu-id="41e2f-105">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="41e2f-106">Bei der Implementierung eines Serialisierungsmechanismus in einer objektorientierten Umgebung muss vielfach zwischen einfacher Handhabung und Flexibilät abgewogen werden.</span><span class="sxs-lookup"><span data-stu-id="41e2f-106">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="41e2f-107">Dieser Vorgang lässt sich größtenteils automatisieren, sofern Sie ausreichend Kontrolle über den Vorgang haben.</span><span class="sxs-lookup"><span data-stu-id="41e2f-107">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="41e2f-108">Es kann beispielsweise Situationen geben, in denen eine einfache binäre Serialisierung nicht ausreichend ist, oder aus einem bestimmt Grund kann es erforderlich sein zu entscheiden, welche Felder einer Klasse serialisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="41e2f-108">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="41e2f-109">In den folgenden Abschnitten wird der robuste Serialisierungsmechanismus untersucht, der von .NET bereitgestellt wird, und es werden einige wichtige Funktionen hervorgehoben, mit denen Sie diesen Vorgang an Ihre Anforderungen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="41e2f-109">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="41e2f-110">Der Zustand eines UTF-8- oder UTF-7-codierten Objektes wird nicht beibehalten, wenn das Objekt mit verschiedenen Versionen von .NET Framework serialisiert und deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="41e2f-110">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="41e2f-111">Die binäre Serialisierung ermöglicht das Ändern privater Member innerhalb eines Objekts und somit die Änderung von deren Zustand.</span><span class="sxs-lookup"><span data-stu-id="41e2f-111">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="41e2f-112">Aus diesem Grund werden andere Serialisierungsframeworks wie <xref:System.Text.Json?displayProperty=fullName> empfohlen, die auf der öffentlichen API-Oberfläche operieren.</span><span class="sxs-lookup"><span data-stu-id="41e2f-112">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="41e2f-113">.NET Core</span><span class="sxs-lookup"><span data-stu-id="41e2f-113">.NET Core</span></span>

<span data-ttu-id="41e2f-114">.NET Core unterstützt binäre Serialisierung für eine Teilmenge der Typen.</span><span class="sxs-lookup"><span data-stu-id="41e2f-114">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="41e2f-115">Die Liste der unterstützten Typen finden Sie im folgenden Abschnitt unter [Serialisierbare Typen](#serializable-types).</span><span class="sxs-lookup"><span data-stu-id="41e2f-115">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="41e2f-116">Die aufgelisteten Typen können zwischen .NET Framework 4.5.1 und höheren Versionen und .NET Core 2.0 und höheren Versionen serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="41e2f-116">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="41e2f-117">Andere Implementierungen von .NET, z. B. Mono, werden nicht offiziell unterstützt, sollten jedoch ebenfalls funktionieren.</span><span class="sxs-lookup"><span data-stu-id="41e2f-117">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="41e2f-118">Serialisierbare Typen</span><span class="sxs-lookup"><span data-stu-id="41e2f-118">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="41e2f-119">Typ</span><span class="sxs-lookup"><span data-stu-id="41e2f-119">Type</span></span> | <span data-ttu-id="41e2f-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41e2f-120">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-121">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-121">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-122">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-122">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-123">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-124">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-125">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-126">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-127">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-128">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-129">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-130">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-131">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-132">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-133">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-134">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-134">Starting in .NET Core 2.0.4.</span></span> |
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
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="41e2f-135">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-136">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-136">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-137">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-138">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-139">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-140">Ab .NET Core 2.0.4</span><span class="sxs-lookup"><span data-stu-id="41e2f-140">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="41e2f-141">die Serialisierung von .NET Framework zu .NET Core wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41e2f-141">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-142">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-142">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="41e2f-143">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-143">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-144">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-145">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-146">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-147">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-148">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-149">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-150">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="41e2f-151">Ab .NET Core 2.0.2 und höheren Versionen</span><span class="sxs-lookup"><span data-stu-id="41e2f-151">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-152">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-153">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-153">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-154">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-155">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="41e2f-156">Wenn Sie `RemotingFormat` auf `SerializationFormat.Binary` festlegen, kann die Eigenschaft nur mit .NET Core 2.1 und höheren Versionen ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="41e2f-156">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-157">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-158">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-158">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-159">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-160">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-161">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-162">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-163">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-164">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-165">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-166">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-167">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-168">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-169">Ab .NET Core 2.0.4,</span><span class="sxs-lookup"><span data-stu-id="41e2f-169">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="41e2f-170">die Serialisierung von .NET Framework zu .NET Core wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41e2f-170">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-171">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-171">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-172">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-172">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-173">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-174">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-175">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-176">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-177">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-178">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-179">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="41e2f-180">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-181">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-182">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-183">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-184">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-185">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-186">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-187">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-188">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-189">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-190">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-191">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-192">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-193">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-194">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-195">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-196">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-197">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-198">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-199">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-200">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-201">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-202">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-203">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-204">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-205">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="41e2f-206">Ab .NET Core 2.0.6</span><span class="sxs-lookup"><span data-stu-id="41e2f-206">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-207">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-208">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-208">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-209">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-210">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="41e2f-211">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-212">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-213">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-214">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-215">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-216">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-217">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-218">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-219">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-220">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-221">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-222">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-223">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-224">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-225">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-226">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-227">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-228">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-229">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-230">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-231">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-232">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-233">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-234">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-235">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-236">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-237">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-238">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-239">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-240">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-241">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-242">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-243">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-244">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-245">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-246">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-247">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-248">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-249">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-250">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-251">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-252">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-253">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-254">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-255">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-256">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-257">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-258">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-259">Ab .NET Core 2.0.4,</span><span class="sxs-lookup"><span data-stu-id="41e2f-259">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="41e2f-260">die Serialisierung von .NET Framework zu .NET Core wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41e2f-260">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-261">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-261">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-262">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-262">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-263">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-264">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-265">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-266">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-267">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-268">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-269">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-270">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-271">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-272">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-273">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-274">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-275">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-276">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-277">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-278">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-279">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-280">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-281">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-281">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="41e2f-282">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-283">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-283">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-284">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-285">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-286">Ab .NET Core 2.0.4,</span><span class="sxs-lookup"><span data-stu-id="41e2f-286">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="41e2f-287">eingeschränkte Serialisierungsdaten</span><span class="sxs-lookup"><span data-stu-id="41e2f-287">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-288">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-288">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-289">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-289">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-290">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-291">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-292">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-293">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-294">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-295">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-296">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-297">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-298">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-299">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-300">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-301">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-302">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-303">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-304">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-305">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-306">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-307">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-308">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-309">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-310">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-311">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-312">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-313">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-314">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-315">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-316">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-317">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-318">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-319">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-320">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="41e2f-321">Nicht in .NET Framework 4.7 und früheren Versionen serialisierbar</span><span class="sxs-lookup"><span data-stu-id="41e2f-321">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-322">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-323">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-323">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-324">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-325">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-326">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-327">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="41e2f-328">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="41e2f-328">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="41e2f-329">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41e2f-329">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="41e2f-330">Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="41e2f-330">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="41e2f-331">[XML- und SOAP-Serialisierung](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="41e2f-331">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="41e2f-332">Beschreibt den XML-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="41e2f-332">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="41e2f-333">[Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="41e2f-333">[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="41e2f-334">Beschreibt Richtlinien für das Schreiben sicheren Codes, die beim Schreiben von befolgt werden sollten, der Serialisierungen durchführt.</span><span class="sxs-lookup"><span data-stu-id="41e2f-334">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="41e2f-335">[.NET-Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="41e2f-335">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="41e2f-336">Beschreibt die verschiedenen Verfahren für die Remotekommunikation, die ab .NET Framework zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="41e2f-336">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="41e2f-337">[Mit ASP.NET- und XML-Webdienstclients erstellte XML-Webdienste](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="41e2f-337">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="41e2f-338">In diesen Artikeln wird beschrieben und erklärt, wie mit ASP.NET erstellte XML-Webdienste programmiert werden.</span><span class="sxs-lookup"><span data-stu-id="41e2f-338">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
