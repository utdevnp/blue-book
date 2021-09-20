
  const notification  = await HistoryModel.aggregate([
    {
      $lookup: {
        from: "pages",
        localField: "pageId",
        foreignField: "_id",
        as: "page",
      },
    },
    {
      $lookup: {
        from: "customers",
        localField: "customer",
        foreignField: "_id",
        as: "customer",
      },
    },
    {
      $match: QueryData,
    },
    { $unwind: "$page" },

    {
      $sort: {
        createdAt: -1,
      },
    },{
      $limit:5
    }
   

  ]);
