# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Estimate Multinomial Logit Models with Observed and Unobserved Individual Heterogeneity Use gmnl With (In) R Software
install.packages("gmnl")
library("gmnl")
library("mlogit")
gmnl = read.csv("https://raw.githubusercontent.com/timbulwidodostp/gmnl/main/gmnl/gmnl.csv",sep = ";")
# Estimation Estimate Multinomial Logit Models with Observed and Unobserved Individual Heterogeneity Use gmnl With (In) R Software
gmnl <- mlogit.data(gmnl, id.var = "id", choice = "choice", varying = 4:27, shape = "wide", sep = "")
gmnl_1 <- gmnl(choice ~ pf + cl + loc + wk + tod + seas| 0, data = gmnl, subset = 1:3000, model = 'smnl', R = 10,
panel = TRUE, ranp = c(cl = "n", loc = "n", wk = "n", tod = "n", seas = "n"), correlation = TRUE)
summary(gmnl_1)

gmnl_2 <- gmnl(choice ~ pf + cl + loc + wk + tod + seas| 0, data = gmnl, subset = 1:3000, model = 'mixl', R = 10,
panel = TRUE, ranp = c(cl = "n", loc = "n", wk = "n", tod = "n", seas = "n"), correlation = TRUE)
summary(gmnl_2)

gmnl_3 <- gmnl(choice ~ pf + cl + loc + wk + tod + seas| 0, data = gmnl, subset = 1:3000, model = 'gmnl', R = 10,
panel = TRUE, ranp = c(cl = "n", loc = "n", wk = "n", tod = "n", seas = "n"), correlation = TRUE)
summary(gmnl_3)

# Estimate Multinomial Logit Models with Observed and Unobserved Individual Heterogeneity Use gmnl With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished