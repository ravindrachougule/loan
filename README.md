# loan
A Loan calculator for salaried and business client, containing entire life cycle till duedeligence.

As the repository is private, just putting few snippets for reference.


    public static Function<Application, MonetaryAmount> getRepayingCapacity() {
        return application -> application.getGrossMonthlyIncome().orElse(ZERO)
                    .subtract(application.getDeductions().orElse(ZERO))
                    .subtract(application.getBank().getRegulator().getRegulatoryReservedExpenses().apply(application));
    }
