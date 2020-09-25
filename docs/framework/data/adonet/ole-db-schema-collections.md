---
title: OLE DB-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 90899a123b3dafcd47a50ef8f6eb003938b22a03
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186938"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="0fd0f-102">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="0fd0f-102">OLE DB Schema Collections</span></span>

<span data-ttu-id="0fd0f-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="0fd0f-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="0fd0f-104">Microsoft SQL Server-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="0fd0f-104">Microsoft SQL Server OLE DB Provider</span></span>  

 <span data-ttu-id="0fd0f-105">Der Microsoft SQL Server-OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="0fd0f-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="0fd0f-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0fd0f-106">Tables</span></span>  
  
- <span data-ttu-id="0fd0f-107">Spalten</span><span class="sxs-lookup"><span data-stu-id="0fd0f-107">Columns</span></span>  
  
- <span data-ttu-id="0fd0f-108">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0fd0f-108">Procedures</span></span>  
  
- <span data-ttu-id="0fd0f-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0fd0f-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="0fd0f-110">Katalog</span><span class="sxs-lookup"><span data-stu-id="0fd0f-110">Catalog</span></span>  
  
- <span data-ttu-id="0fd0f-111">Indizes</span><span class="sxs-lookup"><span data-stu-id="0fd0f-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="0fd0f-112">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0fd0f-112">Tables</span></span>  
  
|<span data-ttu-id="0fd0f-113">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-113">ColumnName</span></span>|<span data-ttu-id="0fd0f-114">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-115">TABLE_CATALOG</span></span>|<span data-ttu-id="0fd0f-116">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-116">String</span></span>|  
|<span data-ttu-id="0fd0f-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-118">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-118">String</span></span>|  
|<span data-ttu-id="0fd0f-119">table_name</span><span class="sxs-lookup"><span data-stu-id="0fd0f-119">TABLE_NAME</span></span>|<span data-ttu-id="0fd0f-120">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-120">String</span></span>|  
|<span data-ttu-id="0fd0f-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-121">TABLE_TYPE</span></span>|<span data-ttu-id="0fd0f-122">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-122">String</span></span>|  
|<span data-ttu-id="0fd0f-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-123">TABLE_GUID</span></span>|<span data-ttu-id="0fd0f-124">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-124">Guid</span></span>|  
|<span data-ttu-id="0fd0f-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-125">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-126">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-126">String</span></span>|  
|<span data-ttu-id="0fd0f-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-127">TABLE_PROPID</span></span>|<span data-ttu-id="0fd0f-128">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-128">Int64</span></span>|  
|<span data-ttu-id="0fd0f-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-129">DATE_CREATED</span></span>|<span data-ttu-id="0fd0f-130">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-130">DateTime</span></span>|  
|<span data-ttu-id="0fd0f-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-131">DATE_MODIFIED</span></span>|<span data-ttu-id="0fd0f-132">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0fd0f-133">Spalten</span><span class="sxs-lookup"><span data-stu-id="0fd0f-133">Columns</span></span>  
  
|<span data-ttu-id="0fd0f-134">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-134">ColumnName</span></span>|<span data-ttu-id="0fd0f-135">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-136">TABLE_CATALOG</span></span>|<span data-ttu-id="0fd0f-137">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-137">String</span></span>|  
|<span data-ttu-id="0fd0f-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-139">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-139">String</span></span>|  
|<span data-ttu-id="0fd0f-140">table_name</span><span class="sxs-lookup"><span data-stu-id="0fd0f-140">TABLE_NAME</span></span>|<span data-ttu-id="0fd0f-141">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-141">String</span></span>|  
|<span data-ttu-id="0fd0f-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-142">COLUMN_NAME</span></span>|<span data-ttu-id="0fd0f-143">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-143">String</span></span>|  
|<span data-ttu-id="0fd0f-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-144">COLUMN_GUID</span></span>|<span data-ttu-id="0fd0f-145">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-145">Guid</span></span>|  
|<span data-ttu-id="0fd0f-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-146">COLUMN_PROPID</span></span>|<span data-ttu-id="0fd0f-147">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-147">Int64</span></span>|  
|<span data-ttu-id="0fd0f-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="0fd0f-149">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-149">Int64</span></span>|  
|<span data-ttu-id="0fd0f-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0fd0f-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="0fd0f-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-151">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0fd0f-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="0fd0f-153">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-153">String</span></span>|  
|<span data-ttu-id="0fd0f-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0fd0f-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="0fd0f-155">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-155">Int64</span></span>|  
|<span data-ttu-id="0fd0f-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-156">IS_NULLABLE</span></span>|<span data-ttu-id="0fd0f-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-157">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-158">DATA_TYPE</span></span>|<span data-ttu-id="0fd0f-159">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-159">Int32</span></span>|  
|<span data-ttu-id="0fd0f-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-160">TYPE_GUID</span></span>|<span data-ttu-id="0fd0f-161">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-161">Guid</span></span>|  
|<span data-ttu-id="0fd0f-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0fd0f-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0fd0f-163">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-163">Int64</span></span>|  
|<span data-ttu-id="0fd0f-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0fd0f-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0fd0f-165">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-165">Int64</span></span>|  
|<span data-ttu-id="0fd0f-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0fd0f-167">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-167">Int32</span></span>|  
|<span data-ttu-id="0fd0f-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="0fd0f-169">Int16</span><span class="sxs-lookup"><span data-stu-id="0fd0f-169">Int16</span></span>|  
|<span data-ttu-id="0fd0f-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="0fd0f-171">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-171">Int64</span></span>|  
|<span data-ttu-id="0fd0f-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="0fd0f-173">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-173">String</span></span>|  
|<span data-ttu-id="0fd0f-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="0fd0f-175">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-175">String</span></span>|  
|<span data-ttu-id="0fd0f-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="0fd0f-177">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-177">String</span></span>|  
|<span data-ttu-id="0fd0f-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="0fd0f-179">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-179">String</span></span>|  
|<span data-ttu-id="0fd0f-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="0fd0f-181">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-181">String</span></span>|  
|<span data-ttu-id="0fd0f-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-182">COLLATION_NAME</span></span>|<span data-ttu-id="0fd0f-183">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-183">String</span></span>|  
|<span data-ttu-id="0fd0f-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="0fd0f-185">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-185">String</span></span>|  
|<span data-ttu-id="0fd0f-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="0fd0f-187">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-187">String</span></span>|  
|<span data-ttu-id="0fd0f-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-188">DOMAIN_NAME</span></span>|<span data-ttu-id="0fd0f-189">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-189">String</span></span>|  
|<span data-ttu-id="0fd0f-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-190">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-191">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-191">String</span></span>|  
|<span data-ttu-id="0fd0f-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-192">COLUMN_LCID</span></span>|<span data-ttu-id="0fd0f-193">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-193">Int32</span></span>|  
|<span data-ttu-id="0fd0f-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="0fd0f-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="0fd0f-195">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-195">Int32</span></span>|  
|<span data-ttu-id="0fd0f-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-196">COLUMN_SORTID</span></span>|<span data-ttu-id="0fd0f-197">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-197">Int32</span></span>|  
|<span data-ttu-id="0fd0f-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="0fd0f-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="0fd0f-199">Byte[]</span></span>|  
|<span data-ttu-id="0fd0f-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-200">IS_COMPUTED</span></span>|<span data-ttu-id="0fd0f-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0fd0f-202">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0fd0f-202">Procedures</span></span>  
  
|<span data-ttu-id="0fd0f-203">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-203">ColumnName</span></span>|<span data-ttu-id="0fd0f-204">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0fd0f-206">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-206">String</span></span>|  
|<span data-ttu-id="0fd0f-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-208">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-208">String</span></span>|  
|<span data-ttu-id="0fd0f-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="0fd0f-210">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-210">String</span></span>|  
|<span data-ttu-id="0fd0f-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0fd0f-212">Int16</span><span class="sxs-lookup"><span data-stu-id="0fd0f-212">Int16</span></span>|  
|<span data-ttu-id="0fd0f-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="0fd0f-214">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-214">String</span></span>|  
|<span data-ttu-id="0fd0f-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-215">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-216">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-216">String</span></span>|  
|<span data-ttu-id="0fd0f-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-217">DATE_CREATED</span></span>|<span data-ttu-id="0fd0f-218">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-218">DateTime</span></span>|  
|<span data-ttu-id="0fd0f-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-219">DATE_MODIFIED</span></span>|<span data-ttu-id="0fd0f-220">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="0fd0f-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0fd0f-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="0fd0f-222">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-222">ColumnName</span></span>|<span data-ttu-id="0fd0f-223">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0fd0f-225">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-225">String</span></span>|  
|<span data-ttu-id="0fd0f-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-227">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-227">String</span></span>|  
|<span data-ttu-id="0fd0f-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="0fd0f-229">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-229">String</span></span>|  
|<span data-ttu-id="0fd0f-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-230">PARAMETER_NAME</span></span>|<span data-ttu-id="0fd0f-231">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-231">String</span></span>|  
|<span data-ttu-id="0fd0f-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="0fd0f-233">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-233">Int32</span></span>|  
|<span data-ttu-id="0fd0f-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="0fd0f-235">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-235">Int32</span></span>|  
|<span data-ttu-id="0fd0f-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0fd0f-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="0fd0f-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-237">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0fd0f-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="0fd0f-239">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-239">String</span></span>|  
|<span data-ttu-id="0fd0f-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-240">IS_NULLABLE</span></span>|<span data-ttu-id="0fd0f-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-241">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-242">DATA_TYPE</span></span>|<span data-ttu-id="0fd0f-243">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-243">Int32</span></span>|  
|<span data-ttu-id="0fd0f-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0fd0f-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0fd0f-245">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-245">Int64</span></span>|  
|<span data-ttu-id="0fd0f-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0fd0f-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0fd0f-247">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-247">Int64</span></span>|  
|<span data-ttu-id="0fd0f-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0fd0f-249">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-249">Int32</span></span>|  
|<span data-ttu-id="0fd0f-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="0fd0f-251">Int16</span><span class="sxs-lookup"><span data-stu-id="0fd0f-251">Int16</span></span>|  
|<span data-ttu-id="0fd0f-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-252">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-253">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-253">String</span></span>|  
|<span data-ttu-id="0fd0f-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-254">TYPE_NAME</span></span>|<span data-ttu-id="0fd0f-255">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-255">String</span></span>|  
|<span data-ttu-id="0fd0f-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="0fd0f-257">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="0fd0f-258">Katalog</span><span class="sxs-lookup"><span data-stu-id="0fd0f-258">Catalog</span></span>  
  
|<span data-ttu-id="0fd0f-259">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-259">ColumnName</span></span>|<span data-ttu-id="0fd0f-260">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-261">CATALOG_NAME</span></span>|<span data-ttu-id="0fd0f-262">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-262">String</span></span>|  
|<span data-ttu-id="0fd0f-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-263">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-264">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="0fd0f-265">Indizes</span><span class="sxs-lookup"><span data-stu-id="0fd0f-265">Indexes</span></span>  
  
|<span data-ttu-id="0fd0f-266">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-266">ColumnName</span></span>|<span data-ttu-id="0fd0f-267">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-268">TABLE_CATALOG</span></span>|<span data-ttu-id="0fd0f-269">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-269">String</span></span>|  
|<span data-ttu-id="0fd0f-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-271">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-271">String</span></span>|  
|<span data-ttu-id="0fd0f-272">table_name</span><span class="sxs-lookup"><span data-stu-id="0fd0f-272">TABLE_NAME</span></span>|<span data-ttu-id="0fd0f-273">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-273">String</span></span>|  
|<span data-ttu-id="0fd0f-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-274">INDEX_CATALOG</span></span>|<span data-ttu-id="0fd0f-275">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-275">String</span></span>|  
|<span data-ttu-id="0fd0f-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="0fd0f-277">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-277">String</span></span>|  
|<span data-ttu-id="0fd0f-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-278">INDEX_NAME</span></span>|<span data-ttu-id="0fd0f-279">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-279">String</span></span>|  
|<span data-ttu-id="0fd0f-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="0fd0f-280">PRIMARY_KEY</span></span>|<span data-ttu-id="0fd0f-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-281">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-282">UNIQUE</span></span>|<span data-ttu-id="0fd0f-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-283">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-284">CLUSTERED</span></span>|<span data-ttu-id="0fd0f-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-285">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-286">TYPE</span></span>|<span data-ttu-id="0fd0f-287">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-287">Int32</span></span>|  
|<span data-ttu-id="0fd0f-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="0fd0f-288">FILL_FACTOR</span></span>|<span data-ttu-id="0fd0f-289">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-289">Int32</span></span>|  
|<span data-ttu-id="0fd0f-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-290">INITIAL_SIZE</span></span>|<span data-ttu-id="0fd0f-291">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-291">Int32</span></span>|  
|<span data-ttu-id="0fd0f-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="0fd0f-292">NULLS</span></span>|<span data-ttu-id="0fd0f-293">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-293">Int32</span></span>|  
|<span data-ttu-id="0fd0f-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="0fd0f-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="0fd0f-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-295">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-296">AUTO_UPDATE</span></span>|<span data-ttu-id="0fd0f-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-297">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-298">NULL_COLLATION</span></span>|<span data-ttu-id="0fd0f-299">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-299">Int32</span></span>|  
|<span data-ttu-id="0fd0f-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="0fd0f-301">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-301">Int64</span></span>|  
|<span data-ttu-id="0fd0f-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-302">COLUMN_NAME</span></span>|<span data-ttu-id="0fd0f-303">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-303">String</span></span>|  
|<span data-ttu-id="0fd0f-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-304">COLUMN_GUID</span></span>|<span data-ttu-id="0fd0f-305">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-305">Guid</span></span>|  
|<span data-ttu-id="0fd0f-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-306">COLUMN_PROPID</span></span>|<span data-ttu-id="0fd0f-307">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-307">Int64</span></span>|  
|<span data-ttu-id="0fd0f-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-308">COLLATION</span></span>|<span data-ttu-id="0fd0f-309">Int16</span><span class="sxs-lookup"><span data-stu-id="0fd0f-309">Int16</span></span>|  
|<span data-ttu-id="0fd0f-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="0fd0f-310">CARDINALITY</span></span>|<span data-ttu-id="0fd0f-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="0fd0f-311">Decimal</span></span>|  
|<span data-ttu-id="0fd0f-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="0fd0f-312">PAGES</span></span>|<span data-ttu-id="0fd0f-313">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-313">Int32</span></span>|  
|<span data-ttu-id="0fd0f-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-314">FILTER_CONDITION</span></span>|<span data-ttu-id="0fd0f-315">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-315">String</span></span>|  
|<span data-ttu-id="0fd0f-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-316">INTEGRATED</span></span>|<span data-ttu-id="0fd0f-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="0fd0f-318">Microsoft Oracle-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="0fd0f-318">Microsoft Oracle OLE DB Provider</span></span>  

 <span data-ttu-id="0fd0f-319">Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="0fd0f-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="0fd0f-320">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0fd0f-320">Tables</span></span>  
  
- <span data-ttu-id="0fd0f-321">Spalten</span><span class="sxs-lookup"><span data-stu-id="0fd0f-321">Columns</span></span>  
  
- <span data-ttu-id="0fd0f-322">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0fd0f-322">Procedures</span></span>  
  
- <span data-ttu-id="0fd0f-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0fd0f-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="0fd0f-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="0fd0f-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="0fd0f-325">Sichten</span><span class="sxs-lookup"><span data-stu-id="0fd0f-325">Views</span></span>  
  
- <span data-ttu-id="0fd0f-326">Indizes</span><span class="sxs-lookup"><span data-stu-id="0fd0f-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="0fd0f-327">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0fd0f-327">Tables</span></span>  
  
|<span data-ttu-id="0fd0f-328">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-328">ColumnName</span></span>|<span data-ttu-id="0fd0f-329">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-330">TABLE_CATALOG</span></span>|<span data-ttu-id="0fd0f-331">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-331">String</span></span>|  
|<span data-ttu-id="0fd0f-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-333">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-333">String</span></span>|  
|<span data-ttu-id="0fd0f-334">table_name</span><span class="sxs-lookup"><span data-stu-id="0fd0f-334">TABLE_NAME</span></span>|<span data-ttu-id="0fd0f-335">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-335">String</span></span>|  
|<span data-ttu-id="0fd0f-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-336">TABLE_TYPE</span></span>|<span data-ttu-id="0fd0f-337">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-337">String</span></span>|  
|<span data-ttu-id="0fd0f-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-338">TABLE_GUID</span></span>|<span data-ttu-id="0fd0f-339">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-339">Guid</span></span>|  
|<span data-ttu-id="0fd0f-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-340">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-341">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-341">String</span></span>|  
|<span data-ttu-id="0fd0f-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-342">TABLE_PROPID</span></span>|<span data-ttu-id="0fd0f-343">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-343">Int64</span></span>|  
|<span data-ttu-id="0fd0f-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-344">DATE_CREATED</span></span>|<span data-ttu-id="0fd0f-345">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-345">DateTime</span></span>|  
|<span data-ttu-id="0fd0f-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-346">DATE_MODIFIED</span></span>|<span data-ttu-id="0fd0f-347">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0fd0f-348">Spalten</span><span class="sxs-lookup"><span data-stu-id="0fd0f-348">Columns</span></span>  
  
|<span data-ttu-id="0fd0f-349">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-349">ColumnName</span></span>|<span data-ttu-id="0fd0f-350">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-351">TABLE_CATALOG</span></span>|<span data-ttu-id="0fd0f-352">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-352">String</span></span>|  
|<span data-ttu-id="0fd0f-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-354">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-354">String</span></span>|  
|<span data-ttu-id="0fd0f-355">table_name</span><span class="sxs-lookup"><span data-stu-id="0fd0f-355">TABLE_NAME</span></span>|<span data-ttu-id="0fd0f-356">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-356">String</span></span>|  
|<span data-ttu-id="0fd0f-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-357">COLUMN_NAME</span></span>|<span data-ttu-id="0fd0f-358">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-358">String</span></span>|  
|<span data-ttu-id="0fd0f-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-359">COLUMN_GUID</span></span>|<span data-ttu-id="0fd0f-360">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-360">Guid</span></span>|  
|<span data-ttu-id="0fd0f-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-361">COLUMN_PROPID</span></span>|<span data-ttu-id="0fd0f-362">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-362">Int64</span></span>|  
|<span data-ttu-id="0fd0f-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="0fd0f-364">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-364">Int64</span></span>|  
|<span data-ttu-id="0fd0f-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0fd0f-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="0fd0f-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-366">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0fd0f-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="0fd0f-368">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-368">String</span></span>|  
|<span data-ttu-id="0fd0f-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0fd0f-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="0fd0f-370">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-370">Int64</span></span>|  
|<span data-ttu-id="0fd0f-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-371">IS_NULLABLE</span></span>|<span data-ttu-id="0fd0f-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-372">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-373">DATA_TYPE</span></span>|<span data-ttu-id="0fd0f-374">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-374">Int32</span></span>|  
|<span data-ttu-id="0fd0f-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-375">TYPE_GUID</span></span>|<span data-ttu-id="0fd0f-376">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-376">Guid</span></span>|  
|<span data-ttu-id="0fd0f-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0fd0f-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0fd0f-378">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-378">Int64</span></span>|  
|<span data-ttu-id="0fd0f-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0fd0f-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0fd0f-380">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-380">Int64</span></span>|  
|<span data-ttu-id="0fd0f-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0fd0f-382">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-382">Int32</span></span>|  
|<span data-ttu-id="0fd0f-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="0fd0f-384">Int16</span><span class="sxs-lookup"><span data-stu-id="0fd0f-384">Int16</span></span>|  
|<span data-ttu-id="0fd0f-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="0fd0f-386">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-386">Int64</span></span>|  
|<span data-ttu-id="0fd0f-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="0fd0f-388">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-388">String</span></span>|  
|<span data-ttu-id="0fd0f-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="0fd0f-390">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-390">String</span></span>|  
|<span data-ttu-id="0fd0f-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="0fd0f-392">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-392">String</span></span>|  
|<span data-ttu-id="0fd0f-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="0fd0f-394">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-394">String</span></span>|  
|<span data-ttu-id="0fd0f-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="0fd0f-396">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-396">String</span></span>|  
|<span data-ttu-id="0fd0f-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-397">COLLATION_NAME</span></span>|<span data-ttu-id="0fd0f-398">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-398">String</span></span>|  
|<span data-ttu-id="0fd0f-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="0fd0f-400">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-400">String</span></span>|  
|<span data-ttu-id="0fd0f-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="0fd0f-402">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-402">String</span></span>|  
|<span data-ttu-id="0fd0f-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-403">DOMAIN_NAME</span></span>|<span data-ttu-id="0fd0f-404">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-404">String</span></span>|  
|<span data-ttu-id="0fd0f-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-405">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-406">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0fd0f-407">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0fd0f-407">Procedures</span></span>  
  
|<span data-ttu-id="0fd0f-408">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-408">ColumnName</span></span>|<span data-ttu-id="0fd0f-409">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0fd0f-411">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-411">String</span></span>|  
|<span data-ttu-id="0fd0f-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-413">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-413">String</span></span>|  
|<span data-ttu-id="0fd0f-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="0fd0f-415">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-415">String</span></span>|  
|<span data-ttu-id="0fd0f-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0fd0f-417">Int16</span><span class="sxs-lookup"><span data-stu-id="0fd0f-417">Int16</span></span>|  
|<span data-ttu-id="0fd0f-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="0fd0f-419">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-419">String</span></span>|  
|<span data-ttu-id="0fd0f-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-420">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-421">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-421">String</span></span>|  
|<span data-ttu-id="0fd0f-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-422">DATE_CREATED</span></span>|<span data-ttu-id="0fd0f-423">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-423">DateTime</span></span>|  
|<span data-ttu-id="0fd0f-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-424">DATE_MODIFIED</span></span>|<span data-ttu-id="0fd0f-425">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="0fd0f-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="0fd0f-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="0fd0f-427">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-427">ColumnName</span></span>|<span data-ttu-id="0fd0f-428">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0fd0f-430">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-430">String</span></span>|  
|<span data-ttu-id="0fd0f-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-432">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-432">String</span></span>|  
|<span data-ttu-id="0fd0f-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="0fd0f-434">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-434">String</span></span>|  
|<span data-ttu-id="0fd0f-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-435">COLUMN_NAME</span></span>|<span data-ttu-id="0fd0f-436">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-436">String</span></span>|  
|<span data-ttu-id="0fd0f-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-437">COLUMN_GUID</span></span>|<span data-ttu-id="0fd0f-438">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-438">Guid</span></span>|  
|<span data-ttu-id="0fd0f-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-439">COLUMN_PROPID</span></span>|<span data-ttu-id="0fd0f-440">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-440">Int64</span></span>|  
|<span data-ttu-id="0fd0f-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="0fd0f-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="0fd0f-442">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-442">Int64</span></span>|  
|<span data-ttu-id="0fd0f-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="0fd0f-444">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-444">Int64</span></span>|  
|<span data-ttu-id="0fd0f-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-445">IS_NULLABLE</span></span>|<span data-ttu-id="0fd0f-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-446">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-447">DATA_TYPE</span></span>|<span data-ttu-id="0fd0f-448">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-448">Int32</span></span>|  
|<span data-ttu-id="0fd0f-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-449">TYPE_GUID</span></span>|<span data-ttu-id="0fd0f-450">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-450">Guid</span></span>|  
|<span data-ttu-id="0fd0f-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0fd0f-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0fd0f-452">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-452">Int64</span></span>|  
|<span data-ttu-id="0fd0f-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0fd0f-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0fd0f-454">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-454">Int64</span></span>|  
|<span data-ttu-id="0fd0f-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0fd0f-456">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-456">Int32</span></span>|  
|<span data-ttu-id="0fd0f-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="0fd0f-458">Int16</span><span class="sxs-lookup"><span data-stu-id="0fd0f-458">Int16</span></span>|  
|<span data-ttu-id="0fd0f-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-459">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-460">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-460">String</span></span>|  
|<span data-ttu-id="0fd0f-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="0fd0f-461">OVERLOAD</span></span>|<span data-ttu-id="0fd0f-462">Int16</span><span class="sxs-lookup"><span data-stu-id="0fd0f-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="0fd0f-463">Sichten</span><span class="sxs-lookup"><span data-stu-id="0fd0f-463">Views</span></span>  
  
|<span data-ttu-id="0fd0f-464">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-464">ColumnName</span></span>|<span data-ttu-id="0fd0f-465">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-466">TABLE_CATALOG</span></span>|<span data-ttu-id="0fd0f-467">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-467">String</span></span>|  
|<span data-ttu-id="0fd0f-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-469">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-469">String</span></span>|  
|<span data-ttu-id="0fd0f-470">table_name</span><span class="sxs-lookup"><span data-stu-id="0fd0f-470">TABLE_NAME</span></span>|<span data-ttu-id="0fd0f-471">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-471">String</span></span>|  
|<span data-ttu-id="0fd0f-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="0fd0f-473">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-473">String</span></span>|  
|<span data-ttu-id="0fd0f-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-474">CHECK_OPTION</span></span>|<span data-ttu-id="0fd0f-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-475">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-476">IS_UPDATABLE</span></span>|<span data-ttu-id="0fd0f-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-477">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-478">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-479">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-479">String</span></span>|  
|<span data-ttu-id="0fd0f-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-480">DATE_CREATED</span></span>|<span data-ttu-id="0fd0f-481">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-481">DateTime</span></span>|  
|<span data-ttu-id="0fd0f-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-482">DATE_MODIFIED</span></span>|<span data-ttu-id="0fd0f-483">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="0fd0f-484">Indizes</span><span class="sxs-lookup"><span data-stu-id="0fd0f-484">Indexes</span></span>  
  
|<span data-ttu-id="0fd0f-485">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-485">ColumnName</span></span>|<span data-ttu-id="0fd0f-486">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-487">TABLE_CATALOG</span></span>|<span data-ttu-id="0fd0f-488">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-488">String</span></span>|  
|<span data-ttu-id="0fd0f-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-490">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-490">String</span></span>|  
|<span data-ttu-id="0fd0f-491">table_name</span><span class="sxs-lookup"><span data-stu-id="0fd0f-491">TABLE_NAME</span></span>|<span data-ttu-id="0fd0f-492">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-492">String</span></span>|  
|<span data-ttu-id="0fd0f-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-493">INDEX_CATALOG</span></span>|<span data-ttu-id="0fd0f-494">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-494">String</span></span>|  
|<span data-ttu-id="0fd0f-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="0fd0f-496">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-496">String</span></span>|  
|<span data-ttu-id="0fd0f-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-497">INDEX_NAME</span></span>|<span data-ttu-id="0fd0f-498">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-498">String</span></span>|  
|<span data-ttu-id="0fd0f-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="0fd0f-499">PRIMARY_KEY</span></span>|<span data-ttu-id="0fd0f-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-500">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-501">UNIQUE</span></span>|<span data-ttu-id="0fd0f-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-502">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-503">CLUSTERED</span></span>|<span data-ttu-id="0fd0f-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-504">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-505">TYPE</span></span>|<span data-ttu-id="0fd0f-506">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-506">Int32</span></span>|  
|<span data-ttu-id="0fd0f-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="0fd0f-507">FILL_FACTOR</span></span>|<span data-ttu-id="0fd0f-508">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-508">Int32</span></span>|  
|<span data-ttu-id="0fd0f-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-509">INITIAL_SIZE</span></span>|<span data-ttu-id="0fd0f-510">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-510">Int32</span></span>|  
|<span data-ttu-id="0fd0f-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="0fd0f-511">NULLS</span></span>|<span data-ttu-id="0fd0f-512">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-512">Int32</span></span>|  
|<span data-ttu-id="0fd0f-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="0fd0f-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="0fd0f-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-514">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-515">AUTO_UPDATE</span></span>|<span data-ttu-id="0fd0f-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-516">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-517">NULL_COLLATION</span></span>|<span data-ttu-id="0fd0f-518">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-518">Int32</span></span>|  
|<span data-ttu-id="0fd0f-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="0fd0f-520">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-520">Int64</span></span>|  
|<span data-ttu-id="0fd0f-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-521">COLUMN_NAME</span></span>|<span data-ttu-id="0fd0f-522">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-522">String</span></span>|  
|<span data-ttu-id="0fd0f-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-523">COLUMN_GUID</span></span>|<span data-ttu-id="0fd0f-524">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-524">Guid</span></span>|  
|<span data-ttu-id="0fd0f-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-525">COLUMN_PROPID</span></span>|<span data-ttu-id="0fd0f-526">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-526">Int64</span></span>|  
|<span data-ttu-id="0fd0f-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-527">COLLATION</span></span>|<span data-ttu-id="0fd0f-528">Int16</span><span class="sxs-lookup"><span data-stu-id="0fd0f-528">Int16</span></span>|  
|<span data-ttu-id="0fd0f-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="0fd0f-529">CARDINALITY</span></span>|<span data-ttu-id="0fd0f-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="0fd0f-530">Decimal</span></span>|  
|<span data-ttu-id="0fd0f-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="0fd0f-531">PAGES</span></span>|<span data-ttu-id="0fd0f-532">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-532">Int32</span></span>|  
|<span data-ttu-id="0fd0f-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-533">FILTER_CONDITION</span></span>|<span data-ttu-id="0fd0f-534">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-534">String</span></span>|  
|<span data-ttu-id="0fd0f-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-535">INTEGRATED</span></span>|<span data-ttu-id="0fd0f-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="0fd0f-537">Microsoft Jet OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="0fd0f-537">Microsoft Jet OLE DB Provider</span></span>  

 <span data-ttu-id="0fd0f-538">Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="0fd0f-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="0fd0f-539">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0fd0f-539">Tables</span></span>  
  
- <span data-ttu-id="0fd0f-540">Spalten</span><span class="sxs-lookup"><span data-stu-id="0fd0f-540">Columns</span></span>  
  
- <span data-ttu-id="0fd0f-541">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0fd0f-541">Procedures</span></span>  
  
- <span data-ttu-id="0fd0f-542">Sichten</span><span class="sxs-lookup"><span data-stu-id="0fd0f-542">Views</span></span>  
  
- <span data-ttu-id="0fd0f-543">Indizes</span><span class="sxs-lookup"><span data-stu-id="0fd0f-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="0fd0f-544">Tabellen</span><span class="sxs-lookup"><span data-stu-id="0fd0f-544">Tables</span></span>  
  
|<span data-ttu-id="0fd0f-545">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-545">ColumnName</span></span>|<span data-ttu-id="0fd0f-546">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-547">TABLE_CATALOG</span></span>|<span data-ttu-id="0fd0f-548">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-548">String</span></span>|  
|<span data-ttu-id="0fd0f-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-550">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-550">String</span></span>|  
|<span data-ttu-id="0fd0f-551">table_name</span><span class="sxs-lookup"><span data-stu-id="0fd0f-551">TABLE_NAME</span></span>|<span data-ttu-id="0fd0f-552">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-552">String</span></span>|  
|<span data-ttu-id="0fd0f-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-553">TABLE_TYPE</span></span>|<span data-ttu-id="0fd0f-554">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-554">String</span></span>|  
|<span data-ttu-id="0fd0f-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-555">TABLE_GUID</span></span>|<span data-ttu-id="0fd0f-556">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-556">Guid</span></span>|  
|<span data-ttu-id="0fd0f-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-557">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-558">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-558">String</span></span>|  
|<span data-ttu-id="0fd0f-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-559">TABLE_PROPID</span></span>|<span data-ttu-id="0fd0f-560">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-560">Int64</span></span>|  
|<span data-ttu-id="0fd0f-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-561">DATE_CREATED</span></span>|<span data-ttu-id="0fd0f-562">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-562">DateTime</span></span>|  
|<span data-ttu-id="0fd0f-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-563">DATE_MODIFIED</span></span>|<span data-ttu-id="0fd0f-564">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="0fd0f-565">Spalten</span><span class="sxs-lookup"><span data-stu-id="0fd0f-565">Columns</span></span>  
  
|<span data-ttu-id="0fd0f-566">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-566">ColumnName</span></span>|<span data-ttu-id="0fd0f-567">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-568">TABLE_CATALOG</span></span>|<span data-ttu-id="0fd0f-569">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-569">String</span></span>|  
|<span data-ttu-id="0fd0f-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-571">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-571">String</span></span>|  
|<span data-ttu-id="0fd0f-572">table_name</span><span class="sxs-lookup"><span data-stu-id="0fd0f-572">TABLE_NAME</span></span>|<span data-ttu-id="0fd0f-573">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-573">String</span></span>|  
|<span data-ttu-id="0fd0f-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-574">COLUMN_NAME</span></span>|<span data-ttu-id="0fd0f-575">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-575">String</span></span>|  
|<span data-ttu-id="0fd0f-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-576">COLUMN_GUID</span></span>|<span data-ttu-id="0fd0f-577">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-577">Guid</span></span>|  
|<span data-ttu-id="0fd0f-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-578">COLUMN_PROPID</span></span>|<span data-ttu-id="0fd0f-579">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-579">Int64</span></span>|  
|<span data-ttu-id="0fd0f-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="0fd0f-581">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-581">Int64</span></span>|  
|<span data-ttu-id="0fd0f-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="0fd0f-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="0fd0f-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-583">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0fd0f-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="0fd0f-585">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-585">String</span></span>|  
|<span data-ttu-id="0fd0f-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0fd0f-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="0fd0f-587">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-587">Int64</span></span>|  
|<span data-ttu-id="0fd0f-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-588">IS_NULLABLE</span></span>|<span data-ttu-id="0fd0f-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-589">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-590">DATA_TYPE</span></span>|<span data-ttu-id="0fd0f-591">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-591">Int32</span></span>|  
|<span data-ttu-id="0fd0f-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-592">TYPE_GUID</span></span>|<span data-ttu-id="0fd0f-593">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-593">Guid</span></span>|  
|<span data-ttu-id="0fd0f-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0fd0f-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="0fd0f-595">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-595">Int64</span></span>|  
|<span data-ttu-id="0fd0f-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="0fd0f-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="0fd0f-597">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-597">Int64</span></span>|  
|<span data-ttu-id="0fd0f-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="0fd0f-599">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-599">Int32</span></span>|  
|<span data-ttu-id="0fd0f-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="0fd0f-601">Int16</span><span class="sxs-lookup"><span data-stu-id="0fd0f-601">Int16</span></span>|  
|<span data-ttu-id="0fd0f-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="0fd0f-603">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-603">Int64</span></span>|  
|<span data-ttu-id="0fd0f-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="0fd0f-605">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-605">String</span></span>|  
|<span data-ttu-id="0fd0f-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="0fd0f-607">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-607">String</span></span>|  
|<span data-ttu-id="0fd0f-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="0fd0f-609">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-609">String</span></span>|  
|<span data-ttu-id="0fd0f-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="0fd0f-611">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-611">String</span></span>|  
|<span data-ttu-id="0fd0f-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="0fd0f-613">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-613">String</span></span>|  
|<span data-ttu-id="0fd0f-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-614">COLLATION_NAME</span></span>|<span data-ttu-id="0fd0f-615">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-615">String</span></span>|  
|<span data-ttu-id="0fd0f-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="0fd0f-617">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-617">String</span></span>|  
|<span data-ttu-id="0fd0f-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="0fd0f-619">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-619">String</span></span>|  
|<span data-ttu-id="0fd0f-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-620">DOMAIN_NAME</span></span>|<span data-ttu-id="0fd0f-621">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-621">String</span></span>|  
|<span data-ttu-id="0fd0f-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-622">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-623">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="0fd0f-624">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="0fd0f-624">Procedures</span></span>  
  
|<span data-ttu-id="0fd0f-625">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-625">ColumnName</span></span>|<span data-ttu-id="0fd0f-626">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="0fd0f-628">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-628">String</span></span>|  
|<span data-ttu-id="0fd0f-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-630">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-630">String</span></span>|  
|<span data-ttu-id="0fd0f-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="0fd0f-632">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-632">String</span></span>|  
|<span data-ttu-id="0fd0f-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="0fd0f-634">Int16</span><span class="sxs-lookup"><span data-stu-id="0fd0f-634">Int16</span></span>|  
|<span data-ttu-id="0fd0f-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="0fd0f-636">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-636">String</span></span>|  
|<span data-ttu-id="0fd0f-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-637">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-638">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-638">String</span></span>|  
|<span data-ttu-id="0fd0f-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-639">DATE_CREATED</span></span>|<span data-ttu-id="0fd0f-640">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-640">DateTime</span></span>|  
|<span data-ttu-id="0fd0f-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-641">DATE_MODIFIED</span></span>|<span data-ttu-id="0fd0f-642">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="0fd0f-643">Sichten</span><span class="sxs-lookup"><span data-stu-id="0fd0f-643">Views</span></span>  
  
|<span data-ttu-id="0fd0f-644">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-644">ColumnName</span></span>|<span data-ttu-id="0fd0f-645">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-646">TABLE_CATALOG</span></span>|<span data-ttu-id="0fd0f-647">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-647">String</span></span>|  
|<span data-ttu-id="0fd0f-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-649">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-649">String</span></span>|  
|<span data-ttu-id="0fd0f-650">table_name</span><span class="sxs-lookup"><span data-stu-id="0fd0f-650">TABLE_NAME</span></span>|<span data-ttu-id="0fd0f-651">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-651">String</span></span>|  
|<span data-ttu-id="0fd0f-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="0fd0f-653">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-653">String</span></span>|  
|<span data-ttu-id="0fd0f-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-654">CHECK_OPTION</span></span>|<span data-ttu-id="0fd0f-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-655">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-656">IS_UPDATABLE</span></span>|<span data-ttu-id="0fd0f-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-657">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-658">DESCRIPTION</span></span>|<span data-ttu-id="0fd0f-659">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-659">String</span></span>|  
|<span data-ttu-id="0fd0f-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-660">DATE_CREATED</span></span>|<span data-ttu-id="0fd0f-661">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-661">DateTime</span></span>|  
|<span data-ttu-id="0fd0f-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-662">DATE_MODIFIED</span></span>|<span data-ttu-id="0fd0f-663">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fd0f-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="0fd0f-664">Indizes</span><span class="sxs-lookup"><span data-stu-id="0fd0f-664">Indexes</span></span>  
  
|<span data-ttu-id="0fd0f-665">ColumnName</span><span class="sxs-lookup"><span data-stu-id="0fd0f-665">ColumnName</span></span>|<span data-ttu-id="0fd0f-666">DataType</span><span class="sxs-lookup"><span data-stu-id="0fd0f-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="0fd0f-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-667">TABLE_CATALOG</span></span>|<span data-ttu-id="0fd0f-668">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-668">String</span></span>|  
|<span data-ttu-id="0fd0f-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="0fd0f-670">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-670">String</span></span>|  
|<span data-ttu-id="0fd0f-671">table_name</span><span class="sxs-lookup"><span data-stu-id="0fd0f-671">TABLE_NAME</span></span>|<span data-ttu-id="0fd0f-672">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-672">String</span></span>|  
|<span data-ttu-id="0fd0f-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="0fd0f-673">INDEX_CATALOG</span></span>|<span data-ttu-id="0fd0f-674">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-674">String</span></span>|  
|<span data-ttu-id="0fd0f-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="0fd0f-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="0fd0f-676">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-676">String</span></span>|  
|<span data-ttu-id="0fd0f-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-677">INDEX_NAME</span></span>|<span data-ttu-id="0fd0f-678">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-678">String</span></span>|  
|<span data-ttu-id="0fd0f-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="0fd0f-679">PRIMARY_KEY</span></span>|<span data-ttu-id="0fd0f-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-680">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-681">UNIQUE</span></span>|<span data-ttu-id="0fd0f-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-682">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-683">CLUSTERED</span></span>|<span data-ttu-id="0fd0f-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-684">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-685">TYPE</span></span>|<span data-ttu-id="0fd0f-686">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-686">Int32</span></span>|  
|<span data-ttu-id="0fd0f-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="0fd0f-687">FILL_FACTOR</span></span>|<span data-ttu-id="0fd0f-688">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-688">Int32</span></span>|  
|<span data-ttu-id="0fd0f-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-689">INITIAL_SIZE</span></span>|<span data-ttu-id="0fd0f-690">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-690">Int32</span></span>|  
|<span data-ttu-id="0fd0f-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="0fd0f-691">NULLS</span></span>|<span data-ttu-id="0fd0f-692">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-692">Int32</span></span>|  
|<span data-ttu-id="0fd0f-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="0fd0f-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="0fd0f-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-694">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="0fd0f-695">AUTO_UPDATE</span></span>|<span data-ttu-id="0fd0f-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-696">Boolean</span></span>|  
|<span data-ttu-id="0fd0f-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-697">NULL_COLLATION</span></span>|<span data-ttu-id="0fd0f-698">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-698">Int32</span></span>|  
|<span data-ttu-id="0fd0f-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="0fd0f-700">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-700">Int64</span></span>|  
|<span data-ttu-id="0fd0f-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="0fd0f-701">COLUMN_NAME</span></span>|<span data-ttu-id="0fd0f-702">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-702">String</span></span>|  
|<span data-ttu-id="0fd0f-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-703">COLUMN_GUID</span></span>|<span data-ttu-id="0fd0f-704">Guid</span><span class="sxs-lookup"><span data-stu-id="0fd0f-704">Guid</span></span>|  
|<span data-ttu-id="0fd0f-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="0fd0f-705">COLUMN_PROPID</span></span>|<span data-ttu-id="0fd0f-706">Int64</span><span class="sxs-lookup"><span data-stu-id="0fd0f-706">Int64</span></span>|  
|<span data-ttu-id="0fd0f-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-707">COLLATION</span></span>|<span data-ttu-id="0fd0f-708">Int16</span><span class="sxs-lookup"><span data-stu-id="0fd0f-708">Int16</span></span>|  
|<span data-ttu-id="0fd0f-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="0fd0f-709">CARDINALITY</span></span>|<span data-ttu-id="0fd0f-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="0fd0f-710">Decimal</span></span>|  
|<span data-ttu-id="0fd0f-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="0fd0f-711">PAGES</span></span>|<span data-ttu-id="0fd0f-712">Int32</span><span class="sxs-lookup"><span data-stu-id="0fd0f-712">Int32</span></span>|  
|<span data-ttu-id="0fd0f-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="0fd0f-713">FILTER_CONDITION</span></span>|<span data-ttu-id="0fd0f-714">String</span><span class="sxs-lookup"><span data-stu-id="0fd0f-714">String</span></span>|  
|<span data-ttu-id="0fd0f-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="0fd0f-715">INTEGRATED</span></span>|<span data-ttu-id="0fd0f-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="0fd0f-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0fd0f-717">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0fd0f-717">See also</span></span>

- [<span data-ttu-id="0fd0f-718">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="0fd0f-718">ADO.NET Overview</span></span>](ado-net-overview.md)
