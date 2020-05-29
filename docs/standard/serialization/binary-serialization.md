---
title: Binäre Serialisierung
description: In diesem Artikel werden binäre Serialisierung und Typen beschrieben, die .NET Core dafür unterstützt. Beachten Sie die Gefahren der binären Serialisierung und berücksichtigen Sie Alternativen.
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
ms.openlocfilehash: 4ed76437b743da842d6ba07d29fe7985f824abf0
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421279"
---
# <a name="binary-serialization"></a><span data-ttu-id="eded3-104">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="eded3-104">Binary serialization</span></span>

<span data-ttu-id="eded3-105">Die Serialisierung kann als Prozess der Speicherung eines Objektzustands in einem Speichermedium definiert werden.</span><span class="sxs-lookup"><span data-stu-id="eded3-105">Serialization can be defined as the process of storing the state of an object to a storage medium.</span></span> <span data-ttu-id="eded3-106">Im Rahmen dieses Vorgangs werden die öffentlichen und privaten Felder des Objekts und der Name der Klasse, einschließlich der Assembly, die die Klasse enthält, in einen Bytestream umgewandelt, der dann in einen Datenstream geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="eded3-106">During this process, the public and private fields of the object and the name of the class, including the assembly containing the class, are converted to a stream of bytes, which is then written to a data stream.</span></span> <span data-ttu-id="eded3-107">Wenn das Objekt anschließend deserialisiert wird, wird ein genauer Klon des ursprünglichen Objekts erstellt.</span><span class="sxs-lookup"><span data-stu-id="eded3-107">When the object is subsequently deserialized, an exact clone of the original object is created.</span></span>

<span data-ttu-id="eded3-108">Bei der Implementierung eines Serialisierungsmechanismus in einer objektorientierten Umgebung muss vielfach zwischen einfacher Handhabung und Flexibilät abgewogen werden.</span><span class="sxs-lookup"><span data-stu-id="eded3-108">When implementing a serialization mechanism in an object-oriented environment, you have to make a number of tradeoffs between ease of use and flexibility.</span></span> <span data-ttu-id="eded3-109">Dieser Vorgang lässt sich größtenteils automatisieren, sofern Sie ausreichend Kontrolle über den Vorgang haben.</span><span class="sxs-lookup"><span data-stu-id="eded3-109">The process can be automated to a large extent, provided you are given sufficient control over the process.</span></span> <span data-ttu-id="eded3-110">Es kann beispielsweise Situationen geben, in denen eine einfache binäre Serialisierung nicht ausreichend ist, oder aus einem bestimmt Grund kann es erforderlich sein zu entscheiden, welche Felder einer Klasse serialisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="eded3-110">For example, situations may arise where simple binary serialization is not sufficient, or there might be a specific reason to decide which fields in a class need to be serialized.</span></span> <span data-ttu-id="eded3-111">In den folgenden Abschnitten wird der robuste Serialisierungsmechanismus untersucht, der von .NET bereitgestellt wird, und es werden einige wichtige Funktionen hervorgehoben, mit denen Sie diesen Vorgang an Ihre Anforderungen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="eded3-111">The following sections examine the robust serialization mechanism provided with .NET and highlight a number of important features that allow you to customize the process to meet your needs.</span></span>

> [!NOTE]
> <span data-ttu-id="eded3-112">Der Zustand eines UTF-8- oder UTF-7-codierten Objektes wird nicht beibehalten, wenn das Objekt mit verschiedenen Versionen von .NET Framework serialisiert und deserialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="eded3-112">The state of a UTF-8 or UTF-7 encoded object is not preserved if the object is serialized and deserialized using different .NET Framework versions.</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

<span data-ttu-id="eded3-113">Die binäre Serialisierung ermöglicht das Ändern privater Member innerhalb eines Objekts und somit die Änderung von deren Zustand.</span><span class="sxs-lookup"><span data-stu-id="eded3-113">Binary serialization allows modifying private members inside an object and therefore changing the state of it.</span></span> <span data-ttu-id="eded3-114">Aus diesem Grund werden andere Serialisierungsframeworks wie <xref:System.Text.Json?displayProperty=fullName> empfohlen, die auf der öffentlichen API-Oberfläche operieren.</span><span class="sxs-lookup"><span data-stu-id="eded3-114">Because of this, other serialization frameworks, like <xref:System.Text.Json?displayProperty=fullName>, that operate on the public API surface are recommended.</span></span>

## <a name="net-core"></a><span data-ttu-id="eded3-115">.NET Core</span><span class="sxs-lookup"><span data-stu-id="eded3-115">.NET Core</span></span>

<span data-ttu-id="eded3-116">.NET Core unterstützt binäre Serialisierung für eine Teilmenge der Typen.</span><span class="sxs-lookup"><span data-stu-id="eded3-116">.NET Core supports binary serialization for a subset of types.</span></span> <span data-ttu-id="eded3-117">Die Liste der unterstützten Typen finden Sie im folgenden Abschnitt unter [Serialisierbare Typen](#serializable-types).</span><span class="sxs-lookup"><span data-stu-id="eded3-117">You can see the list of supported types in the [Serializable types](#serializable-types) section that follows.</span></span> <span data-ttu-id="eded3-118">Die aufgelisteten Typen können zwischen .NET Framework 4.5.1 und höheren Versionen und .NET Core 2.0 und höheren Versionen serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="eded3-118">The listed types are guaranteed to be serializable between .NET Framework 4.5.1 and later versions and between .NET Core 2.0 and later versions.</span></span> <span data-ttu-id="eded3-119">Andere Implementierungen von .NET, z. B. Mono, werden nicht offiziell unterstützt, sollten jedoch ebenfalls funktionieren.</span><span class="sxs-lookup"><span data-stu-id="eded3-119">Other .NET implementations, such as Mono, aren't officially supported but should also work.</span></span>

### <a name="serializable-types"></a><span data-ttu-id="eded3-120">Serialisierbare Typen</span><span class="sxs-lookup"><span data-stu-id="eded3-120">Serializable types</span></span>

> [!div class="mx-tdCol2BreakAll"]
> | <span data-ttu-id="eded3-121">Typ</span><span class="sxs-lookup"><span data-stu-id="eded3-121">Type</span></span> | <span data-ttu-id="eded3-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eded3-122">Notes</span></span> |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | <span data-ttu-id="eded3-123">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-123">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | <span data-ttu-id="eded3-124">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-124">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-125">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-125">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AggregateException?displayProperty=nameWithType> | <span data-ttu-id="eded3-126">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-126">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-127">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-127">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-128">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-128">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | <span data-ttu-id="eded3-129">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-129">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | <span data-ttu-id="eded3-130">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-130">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="eded3-131">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-131">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | <span data-ttu-id="eded3-132">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-132">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="eded3-133">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-133">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | <span data-ttu-id="eded3-134">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-134">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | <span data-ttu-id="eded3-135">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-135">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="eded3-136">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-136">Starting in .NET Core 2.0.4.</span></span> |
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
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | <span data-ttu-id="eded3-137">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-137">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-138">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-138">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | <span data-ttu-id="eded3-139">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-139">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | <span data-ttu-id="eded3-140">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-140">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | <span data-ttu-id="eded3-141">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-141">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | <span data-ttu-id="eded3-142">Ab .NET Core 2.0.4</span><span class="sxs-lookup"><span data-stu-id="eded3-142">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="eded3-143">die Serialisierung von .NET Framework zu .NET Core wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eded3-143">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | <span data-ttu-id="eded3-144">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-144">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | <span data-ttu-id="eded3-145">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-145">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | <span data-ttu-id="eded3-146">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-146">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-147">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-147">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | <span data-ttu-id="eded3-148">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-148">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="eded3-149">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-149">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="eded3-150">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-150">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | <span data-ttu-id="eded3-151">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-151">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | <span data-ttu-id="eded3-152">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-152">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DBNull?displayProperty=nameWithType> | <span data-ttu-id="eded3-153">Ab .NET Core 2.0.2 und höheren Versionen</span><span class="sxs-lookup"><span data-stu-id="eded3-153">Starting in .NET Core 2.0.2 and later versions.</span></span> |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | <span data-ttu-id="eded3-154">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-154">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | <span data-ttu-id="eded3-155">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-155">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | <span data-ttu-id="eded3-156">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-156">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | <span data-ttu-id="eded3-157">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-157">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | <span data-ttu-id="eded3-158">Wenn Sie `RemotingFormat` auf `SerializationFormat.Binary` festlegen, kann die Eigenschaft nur mit .NET Core 2.1 und höheren Versionen ausgetauscht werden.</span><span class="sxs-lookup"><span data-stu-id="eded3-158">If you set `RemotingFormat` to `SerializationFormat.Binary`, it can only be exchanged with .NET Core 2.1 and later versions.</span></span> |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | <span data-ttu-id="eded3-159">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-159">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | <span data-ttu-id="eded3-160">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-160">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | <span data-ttu-id="eded3-161">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-161">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | <span data-ttu-id="eded3-162">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-162">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | <span data-ttu-id="eded3-163">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-163">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | <span data-ttu-id="eded3-164">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-164">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | <span data-ttu-id="eded3-165">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-165">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-166">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-166">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | <span data-ttu-id="eded3-167">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-167">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-168">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-168">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | <span data-ttu-id="eded3-169">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-169">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | <span data-ttu-id="eded3-170">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-170">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | <span data-ttu-id="eded3-171">Ab .NET Core 2.0.4,</span><span class="sxs-lookup"><span data-stu-id="eded3-171">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="eded3-172">die Serialisierung von .NET Framework zu .NET Core wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eded3-172">Serialization from .NET Framework to .NET Core is not supported</span></span> |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | <span data-ttu-id="eded3-173">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-173">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | <span data-ttu-id="eded3-174">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-174">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | <span data-ttu-id="eded3-175">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-175">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | <span data-ttu-id="eded3-176">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-176">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | <span data-ttu-id="eded3-177">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-177">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | <span data-ttu-id="eded3-178">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-178">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | <span data-ttu-id="eded3-179">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-179">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="eded3-180">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-180">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-181">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-181">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | <span data-ttu-id="eded3-182">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-182">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | <span data-ttu-id="eded3-183">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-183">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="eded3-184">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-184">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | <span data-ttu-id="eded3-185">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-185">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | <span data-ttu-id="eded3-186">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-186">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | <span data-ttu-id="eded3-187">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-187">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | <span data-ttu-id="eded3-188">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-188">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | <span data-ttu-id="eded3-189">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-189">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-190">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-190">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | <span data-ttu-id="eded3-191">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-191">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | <span data-ttu-id="eded3-192">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-192">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="eded3-193">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-193">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-194">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-194">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | <span data-ttu-id="eded3-195">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-195">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | <span data-ttu-id="eded3-196">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-196">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-197">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-197">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | <span data-ttu-id="eded3-198">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-198">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | <span data-ttu-id="eded3-199">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-199">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | <span data-ttu-id="eded3-200">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-200">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-201">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-201">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | <span data-ttu-id="eded3-202">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-202">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-203">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-203">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | <span data-ttu-id="eded3-204">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-204">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="eded3-205">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-205">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | <span data-ttu-id="eded3-206">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-206">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="eded3-207">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-207">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | <span data-ttu-id="eded3-208">Ab .NET Core 2.0.6</span><span class="sxs-lookup"><span data-stu-id="eded3-208">Starting in .NET Core 2.0.6.</span></span> |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | <span data-ttu-id="eded3-209">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-209">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | <span data-ttu-id="eded3-210">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-210">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.FormatException?displayProperty=nameWithType> | <span data-ttu-id="eded3-211">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-211">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="eded3-212">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-212">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | <span data-ttu-id="eded3-213">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-213">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="eded3-214">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-214">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | <span data-ttu-id="eded3-215">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-215">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | <span data-ttu-id="eded3-216">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-216">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | <span data-ttu-id="eded3-217">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-217">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="eded3-218">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-218">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | <span data-ttu-id="eded3-219">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-219">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | <span data-ttu-id="eded3-220">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-220">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | <span data-ttu-id="eded3-221">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-221">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | <span data-ttu-id="eded3-222">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-222">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | <span data-ttu-id="eded3-223">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-223">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | <span data-ttu-id="eded3-224">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-224">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | <span data-ttu-id="eded3-225">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-225">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | <span data-ttu-id="eded3-226">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-226">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | <span data-ttu-id="eded3-227">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-227">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-228">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-228">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | <span data-ttu-id="eded3-229">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-229">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | <span data-ttu-id="eded3-230">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-230">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | <span data-ttu-id="eded3-231">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-231">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | <span data-ttu-id="eded3-232">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-232">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | <span data-ttu-id="eded3-233">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-233">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | <span data-ttu-id="eded3-234">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-234">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | <span data-ttu-id="eded3-235">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-235">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-236">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-236">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | <span data-ttu-id="eded3-237">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-237">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | <span data-ttu-id="eded3-238">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-238">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | <span data-ttu-id="eded3-239">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-239">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | <span data-ttu-id="eded3-240">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-240">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | <span data-ttu-id="eded3-241">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-241">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-242">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-242">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | <span data-ttu-id="eded3-243">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-243">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-244">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-244">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | <span data-ttu-id="eded3-245">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-245">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | <span data-ttu-id="eded3-246">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-246">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | <span data-ttu-id="eded3-247">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-247">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | <span data-ttu-id="eded3-248">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-248">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-249">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-249">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-250">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-250">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | <span data-ttu-id="eded3-251">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-251">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-252">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-252">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | <span data-ttu-id="eded3-253">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-253">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | <span data-ttu-id="eded3-254">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-254">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.OverflowException?displayProperty=nameWithType> | <span data-ttu-id="eded3-255">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-255">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-256">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-256">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.RankException?displayProperty=nameWithType> | <span data-ttu-id="eded3-257">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-257">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | <span data-ttu-id="eded3-258">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-258">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | <span data-ttu-id="eded3-259">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-259">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | <span data-ttu-id="eded3-260">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-260">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="eded3-261">Ab .NET Core 2.0.4</span><span class="sxs-lookup"><span data-stu-id="eded3-261">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="eded3-262">die Serialisierung von .NET Framework zu .NET Core wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eded3-262">Serialization from .NET Framework to .NET Core is not supported.</span></span> |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | <span data-ttu-id="eded3-263">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-263">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-264">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-264">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | <span data-ttu-id="eded3-265">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-265">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | <span data-ttu-id="eded3-266">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-266">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | <span data-ttu-id="eded3-267">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-267">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-268">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-268">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | <span data-ttu-id="eded3-269">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-269">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | <span data-ttu-id="eded3-270">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-270">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | <span data-ttu-id="eded3-271">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-271">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | <span data-ttu-id="eded3-272">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-272">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | <span data-ttu-id="eded3-273">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-273">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | <span data-ttu-id="eded3-274">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-274">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | <span data-ttu-id="eded3-275">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-275">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | <span data-ttu-id="eded3-276">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-276">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | <span data-ttu-id="eded3-277">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-277">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-278">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-278">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | <span data-ttu-id="eded3-279">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-279">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-280">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-280">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | <span data-ttu-id="eded3-281">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-281">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | <span data-ttu-id="eded3-282">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-282">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-283">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-283">Starting in .NET Core 2.0.4.</span></span> |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | <span data-ttu-id="eded3-284">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-284">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | <span data-ttu-id="eded3-285">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-285">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | <span data-ttu-id="eded3-286">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-286">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-287">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-287">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | <span data-ttu-id="eded3-288">Ab .NET Core 2.0.4,</span><span class="sxs-lookup"><span data-stu-id="eded3-288">Starting in .NET Core 2.0.4.</span></span><br/><span data-ttu-id="eded3-289">eingeschränkte Serialisierungsdaten</span><span class="sxs-lookup"><span data-stu-id="eded3-289">Limited serialization data.</span></span> |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-290">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-290">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | <span data-ttu-id="eded3-291">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-291">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="eded3-292">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-292">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | <span data-ttu-id="eded3-293">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-293">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | <span data-ttu-id="eded3-294">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-294">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="eded3-295">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-295">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | <span data-ttu-id="eded3-296">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-296">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | <span data-ttu-id="eded3-297">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-297">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | <span data-ttu-id="eded3-298">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-298">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | <span data-ttu-id="eded3-299">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-299">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | <span data-ttu-id="eded3-300">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-300">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | <span data-ttu-id="eded3-301">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-301">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | <span data-ttu-id="eded3-302">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-302">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | <span data-ttu-id="eded3-303">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-303">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | <span data-ttu-id="eded3-304">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-304">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | <span data-ttu-id="eded3-305">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-305">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-306">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-306">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | <span data-ttu-id="eded3-307">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-307">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | <span data-ttu-id="eded3-308">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-308">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-309">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-309">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | <span data-ttu-id="eded3-310">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-310">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | <span data-ttu-id="eded3-311">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-311">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-312">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-312">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | <span data-ttu-id="eded3-313">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-313">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | <span data-ttu-id="eded3-314">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-314">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-315">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-315">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | <span data-ttu-id="eded3-316">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-316">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | <span data-ttu-id="eded3-317">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-317">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-318">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-318">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | <span data-ttu-id="eded3-319">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-319">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | <span data-ttu-id="eded3-320">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-320">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | <span data-ttu-id="eded3-321">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-321">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | <span data-ttu-id="eded3-322">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-322">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | <span data-ttu-id="eded3-323">Nicht in .NET Framework 4.7 und früheren Versionen serialisierbar</span><span class="sxs-lookup"><span data-stu-id="eded3-323">Not serializable in .NET Framework 4.7 and earlier versions.</span></span> |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | <span data-ttu-id="eded3-324">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-324">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | <span data-ttu-id="eded3-325">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-325">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | <span data-ttu-id="eded3-326">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-326">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | <span data-ttu-id="eded3-327">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-327">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | <span data-ttu-id="eded3-328">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-328">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | <span data-ttu-id="eded3-329">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-329">Starting in .NET Core 2.0.4.</span></span> |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | <span data-ttu-id="eded3-330">Ab .NET Core 2.0.4.</span><span class="sxs-lookup"><span data-stu-id="eded3-330">Starting in .NET Core 2.0.4.</span></span> |

## <a name="see-also"></a><span data-ttu-id="eded3-331">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eded3-331">See also</span></span>

- <xref:System.Runtime.Serialization>\
<span data-ttu-id="eded3-332">Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="eded3-332">Contains classes that can be used for serializing and deserializing objects.</span></span>

- <span data-ttu-id="eded3-333">[XML- und SOAP-Serialisierung](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="eded3-333">[XML and SOAP Serialization](../../../docs/standard/serialization/xml-and-soap-serialization.md)</span></span>\
<span data-ttu-id="eded3-334">Beschreibt den XML-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="eded3-334">Describes the XML serialization mechanism that is included with the common language runtime.</span></span>

- <span data-ttu-id="eded3-335">[Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md)</span><span class="sxs-lookup"><span data-stu-id="eded3-335">[Security and Serialization](../../../docs/framework/misc/security-and-serialization.md)</span></span>\
<span data-ttu-id="eded3-336">Beschreibt Richtlinien für das Schreiben sicheren Codes, die beim Schreiben von befolgt werden sollten, der Serialisierungen durchführt.</span><span class="sxs-lookup"><span data-stu-id="eded3-336">Describes the secure coding guidelines to follow when writing code that performs serialization.</span></span>

- <span data-ttu-id="eded3-337">[.NET-Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eded3-337">[.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100))</span></span>\
<span data-ttu-id="eded3-338">Beschreibt die verschiedenen Verfahren für die Remotekommunikation, die ab .NET Framework zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="eded3-338">Describes the various methods Starting in .NET Framework for remote communications.</span></span>

- <span data-ttu-id="eded3-339">[Mit ASP.NET- und XML-Webdienstclients erstellte XML-Webdienste](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eded3-339">[XML Web Services Created Using ASP.NET and XML Web Service Clients](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))</span></span>\
<span data-ttu-id="eded3-340">In diesen Artikeln wird beschrieben und erklärt, wie mit ASP.NET erstellte XML-Webdienste programmiert werden.</span><span class="sxs-lookup"><span data-stu-id="eded3-340">Articles that describe and explain how to program XML Web services created using ASP.NET.</span></span>
