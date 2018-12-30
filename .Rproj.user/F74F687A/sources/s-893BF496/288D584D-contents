#' @title Mail predict test for opencpu
#' @description Mail predict test for opencpu.
#' @name mailPred
#' @aliases mailPred
#' @author Xu Jing
#' @usage mailPreds(id)
#' @param id The row of mial data
#'
#' @import xgboost
#' @import jsonlite
#' @import stats
#' @import utils
#'
#' @export mailPreds
mailPreds <- function(id = '1') {

  message("XGBoost model test on opencpu!")

  spam <- NULL
  xgbmodel <- NULL

  spam_path <- system.file("extdata", "mail_data.rda", package = "mailPred")
  xgbmodel_path <- system.file("extdata", "xgb.rda", package = "mailPred")

  data_spam <- load(spam_path)
  model_xgb <- load(xgbmodel_path)

  x = as.matrix(spam[as.integer(id), -ncol(spam)])
  # y = as.numeric(spam[as.integer(id), ncol(spam)]) - 1
  pred <- predict(xgbmodel,x)
  # print(spam)

  return(list(class = pred,id=id))
}
