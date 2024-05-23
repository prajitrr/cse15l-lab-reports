# Lab Report 3

## Part 1
1. Failure Inducing Input:
```
public class ArrayTests {
	@Test 
	public void testReverseInPlaceFailure() {
    int[] input1 = {1, 2, 3, 4};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{4, 3, 2, 1}, input1);
	}
}
```

2. Input that Passes:
```
public class ArrayTests {
	@Test 
	public void testReverseInPlacePass() {
    int[] input1 = {1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{1}, input1);
	}
}
```

3. Symptom:
![Image](./run.png)

4. Buggy and Fixed Code:
Buggy Code:

```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
}
```

Fixed Code:

```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[i];
    }
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
  }
}
```

5. Bug Fix Reasoning:
The fix addresses the issue because without the fix, the second half of the array's elements will not be set to the first half, since the first half will have been overwritten by the second half. Instead, the fix stores a copy of the array, so that the reversal can be performed by iterating over the copy and setting the original array to have reversed elements, and this will avoid overwriting the second half of the array.

## Part 2
I have chosen the command `grep`.
All the information I am using are from the following websites, [https://docs.oracle.com/cd/E19253-01/806-7612/filesearch-99633/index.html](https://docs.oracle.com/cd/E19253-01/806-7612/filesearch-99633/index.html), and [https://phoenixnap.com/kb/grep-command-linux-unix-examples](https://phoenixnap.com/kb/grep-command-linux-unix-examples).

1. Option 1:
Example 1:
```
(base) prajitrajkumar@tuyihkj31798euoij831 biomed % grep -v a rr74.txt

  
    
      
        Introduction
        immunohistochemistry.
      
      
        
          Mice
        
        
          Exposure environments
        
        
        
        
          Western blotting
        
        
          with A 
          260 /A 
          diluted in depC H 
          determined using 18 S rRNA primers/probes (Applied
          RNA.
        
        
          Immunohistochemistry
        
        
          2 -, NO 
          (Ionics Instrument Business Group, Boulder, CO, USA).
        
        
          P < 0.05 is considered
        
      
      
        Results
        
          respectively; 
          P < 0.001).
        
        
          Western blotting
          As shown in Fig. 2, lung eNOS protein levels were
        
        
          3.5-fold (Fig. 3).
        
        
          Immunohistochemistry
          shown).
        
        
        
      
      
        Discussion
        development.
        21].
        detection in the lungs of hypoxic, hypertensive mice.
        flushed with 10% O 
        different species in cultures [ 31, 32, 33, 34, 35, 36, 37]
        production of NO 
        piglets 
      
      
        Conclusion
        considering studies using NOS-deficient mice. The present
```
This example shows the usage of `grep -v` to search for lines without the character `a`. This can be useful to search for lines without certain keywords in order to filter text. 

Example 2:
```
(base) prajitrajkumar@tuyihkj31798euoij831 biomed % grep -v 1 rr37.txt

  
    
      
        Introduction
        Asthma is a common condition in general medical
        disease severity [ 2]. The hospitalization rate, another
        population-level marker of asthma severity, remains
        substantial [ 2], generating nearly one-half of all US
        health care costs for asthma [ 3]. Hospitalization rates
        for asthma have actually increased in some demographic
        subgroups, such as young adults [ 2] and the urban poor [
        4], despite recent therapeutic advances. Understanding the
        factors underlying hospitalization for asthma could help
        elucidate the recent rise in asthma morbidity.
        Previous studies have identified several factors that
        contribute to increased hospitalization risk among adults
        with asthma. Demographic characteristics, such as poverty,
        low educational attainment, female gender, and
        African-American race, have been associated with a greater
        risk of hospitalization for asthma [ 2, 4, 5, 6, 7, 8, 9,
        asthma care have also been frequently cited as contributing
        separating the independent effects of demographic
        characteristics, health care access, and disease severity
        has been difficult. For instance, the association between
        low income or non-white race and greater asthma
        hospitalization risk is potentially confounded by
        inadequate health care access. Because many studies rely on
        ecologic socioeconomic and hospitalization data,
        individual-level factors - especially asthma severity -
        22].
        In this article, using a prospective cohort study of
        adults with asthma, we delineate the relative impact of
        demographic characteristics and asthma severity on
        subsequent hospitalization for asthma. Since study subjects
        were recruited from a random sample of physician practices,
        they all had access to health care for asthma. As a result,
        we could evaluate the effects of gender, race, income, and
        asthma severity on hospitalization, independent of health
        care access.
      
      
        Materials and methods
        
          Subject recruitment and retention
          We used data collected during a prospective,
          longitudinal cohort study of adults with asthma recruited
          from physician practices in Northern California. Details
          of the study design have been previously reported [ 23,
          24, 25, 26]. Each subject underwent a structured,
          computer-assisted telephone interview covering
          demographic characteristics, smoking history, asthma
          history, symptoms, and treatment, health status, health
          care utilization for asthma, and insurance for asthma
          care.
          Physicians registered 669 eligible patients. After
          initial data collection at baseline ( 
          interviews ( 
          n = 539), we later restricted the
          registry) and 242 of the follow-up subjects (65% of
          restricted baseline cohort). We restricted the data set
          to eliminate all interviews potentially compromised by
          faulty data collection or documentation by a single
          survey interviewer [ 26, 27]. This restricted data set
          excluded 24 baseline subjects who were found to be
          outside the study age range and 206 baseline subjects
          with inconsistent data during subsequent re-interview. Of
          who had inconsistent data at later interviews or did not
          month). These exclusions had no significant effect on
          study findings.
          Demographic data for comparison of the baseline cohort
          ( 
          
          n = 669) are not available.
          Compared with subjects who participated in both baseline
          and follow-up interviews ( 
          n = 242), subjects without complete
          follow-up interviews ( 
          versus 40.5 years) and less likely to have white
          no statistical differences in history of ever smoking
          (43% of participants in both interviews versus 37% of
          non-participants at follow-up), female gender (73% versus
          66%), atopic history (82% versus 83%), or
        
        
          Hospitalization for asthma
          The primary study outcome was self-reported
          prospective follow-up period. Subjects were asked at
          Although subjects could indicate more than one positive
          response, we analyzed the binary outcome of one or more
          hospitalization for asthma.
        
        
          Risk factor variables
          All demographic variables were based on baseline
          subject interview responses. Current and prior cigarette
          smoking history was assessed using questions adapted from
          the National Health Interview Survey [ 28].
          disease-specific severity-of-asthma score with four
          subscales: frequency of current asthma symptoms (daytime
          or nocturnal), use of systemic corticosteroids, use of
          other asthma medications (besides systemic
          corticosteroids), and history of hospitalizations and
          intubations [ 23, 24, 25]. Possible total scores range
          from 0 to 28, with higher scores reflecting more severe
          asthma. To examine the relative impact of recent and
          remote hospitalization on further hospitalization for
          asthma over longitudinal follow-up, we removed
          hospitalization from the established severity score and
          defined two new variables: recent hospitalization (during
          hospitalization (past hospitalization not meeting the
          previous definition of recent). As a result, the
          hospitalization and intubation subscale now reflects only
          prior history of intubation.
          Several other clinical aspects of asthma were
          assessed. We defined asthma onset as the subject-reported
          age of first asthma symptoms. Atopic history was defined
          by a reported history of allergic rhinitis or atopic
          dermatitis. Because prior work suggests an unexpectedly
          high prevalence of aspirin intolerance in persons with
          near fatal asthma [ 29], we ascertained any history of
          aspirin sensitivity at baseline interview. Since
          gastroesophageal reflux disease (GERD) may exacerbate
          asthma symptoms [ 30], we evaluated whether subjects were
          taking H2-blockers or proton pump inhibitors as
          surrogates for GERD and related conditions. We
          furthermore determined whether subjects possessed a peak
          flow meter for home usage.
          Generic health status was measured using the Medical
          several indicators of health care access for asthma care,
          including whether subjects had a regular site for asthma
          care, a principal care provider for asthma, medical
          insurance for outpatient asthma care, and an annual
          deduction for outpatient medical care. We also identified
          subjects who appeared to rely on emergency department
          (ED) services for urgent asthma care. We defined reliance
          on ED care as one or more self-reported ED visits during
          the interview interval but no urgent outpatient clinic or
          office visits for asthma, either to regular or alternate
          sources of asthma care.
        
        
          Statistical analysis
          In a previous analysis of pulmonary and allergy
          specialist care, the severity-of-asthma score was
          associated with an increased risk of hospitalization at
          other risk factors for asthma-related hospitalization,
          taking baseline asthma severity into account. Because
          asthma severity may act on the causal pathway between a
          risk factor and subsequent hospitalization for asthma, we
          present multivariate models both including and excluding
          baseline asthma severity and generic health status. For
          example, low education could increase the risk of
          hospitalization either directly, through poor
          self-management strategies, or indirectly, if poorly
          educated persons have greater asthma severity for other
          reasons. We also delineate the components of asthma
          severity - respiratory symptoms, systemic corticosteroid
          use, other asthma medication use, past intubations, and
          previous hospitalizations - that are most strongly
          predictive of subsequent hospitalization.
          (SAS Institute, Cary, NC, USA). We evaluated the
          association between baseline characteristics and the risk
          use the data set restricted to 242 subjects with verified
          baseline and follow-up interviews for all analyses.
          Bivariate relationships were examined using logistic
          regression analysis, with separate models for each
          predictor variable. We used multiple logistic regression
          analysis to elucidate the independent association between
          each baseline variable and the prospective risk of
          hospitalization. In constructing the multivariate model,
          all predictor variables whose bivariate odds ratio and
          95% confidence interval suggested a possible association
          with hospitalization were entered into the final model.
          All variables deemed important on an a priori basis, such
          as age, were also included.
        
      
      
        Results
        
          Health care access
          Reflecting the sampling method employed, all subjects
          identified a regular source of asthma care and a primary
          medical provider for asthma care at baseline interview.
          The majority of participants (97%) also reported having
          health insurance covering outpatient visits for asthma.
          Approximately one-third of subjects indicated having
          The majority of subjects continued to report health
          insurance coverage (96%) and ongoing primary asthma care
          appeared to rely on the ED for urgent asthma care.
        
        
          Demographic factors and the risk of
          hospitalization: bivariate analysis
          and the majority of subjects were female (73%). A
          substantial proportion reported ever smoking cigarettes
          (43%), with fewer indicating current smoking (7%). The
          majority of subjects indicated white, non-Hispanic
          hospitalization for asthma during the prospective
          associated with a greater risk of hospitalization for
          smokers had an increased likelihood of hospitalization,
          although the confidence interval did not exclude no
          association. Greater educational attainment was related
          to a lower risk of hospitalization (OR, 0.8 per year of
          education; 95% CI, 0.70-0.96).
        
        
          Clinical risk factors for hospitalization:
          bivariate analysis
          A greater severity-of-asthma score, excluding its
          hospitalization component, was associated with a higher
          risk of subsequent hospitalization for asthma (OR, 4.7
          per 5-point score increment; 95% CI, 2.9-7.7) (Table 2).
          Although remote asthma hospitalization did not appear
          related to risk of ensuing hospitalization, more recent
          hospitalization was strongly associated with increased
          variables that may reflect exacerbating factors, such as
          aspirin allergy and use of gastric acid suppression
          medication, were also associated with a greater risk of
          asthma hospitalization.
          Better baseline generic physical health status (SF-36)
          was associated with a slightly decreased risk of
          point score increment; 95% CI, 3-9%) (Table 2). Mental
          health status was furthermore associated with a 4%
          CI, 0-7%). Reliance on emergency department care was
          finally related to a greater risk of hospitalization (OR,
        
        
          Risk of hospitalization - multivariate
          analysis
          We examined the independent impact of selected
          covariates on the prospective risk of hospitalization for
          asthma using multiple logistic regression analysis (Table
          3). Of the demographic characteristics, non-white race
          was associated with a greater risk of subsequent asthma
          controlling for asthma severity and the other covariates
          shown. Lower household income was also related to a
          decrement), although the 95% confidence interval did not
          Controlling for demographic and other variables, greater
          severity-of-asthma score (OR, 3.4 per 5-point increment;
          an increased risk of hospitalization. Reliance on ED for
          urgent asthma care was also related to greater risk.
          We examined the relation between race and
          hospitalization in more detail. African-American race was
          associated with an increased risk of hospitalization for
          asthma, compared with white, non-Hispanic persons, after
          Hispanic race/ethnicity also appeared related to
          apparent relation between Asian race and risk of hospital
          To further examine the association between asthma
          severity and hospitalization, we repeated the
          multivariate analysis dividing the overall
          severity-of-asthma score into its four subscales. The
          for asthma (OR, 9.7; 95% CI, 2.2-43.0) were significantly
          associated with an increased risk of asthma
          hospitalization, after controlling for covariates. There
          was, conversely, no statistical relationship between
          ensuing risk of hospitalization. Systemic corticosteroid
          use and recent asthma hospitalization, then, appear to
          drive the relationship between asthma severity and
          hospitalization for asthma.
          Because asthma severity could act as a causal
          intermediate between a risk factor and the risk of
          hospitalization, we repeated the multivariate analysis
          excluding asthma severity and generic health status from
          the model (Table 3). In this analysis, low income was
          more strongly related to a greater risk of
          Use of gastric acid suppression therapy was also
          associated with increased risk (OR, 2.2; 95% CI,
          intervals changed slightly, there were no other notable
          changes compared with the model controlling for asthma
          severity.
          To examine whether subjects without baseline health
          insurance coverage (3%) were affecting study results, we
          repeated the multivariate analysis excluding these
          subjects. Only one of the 39 subjects hospitalized at
          follow-up had no baseline health insurance. There was no
          meaningful impact on the results in all multivariate
          analyses. For example, the estimate for lower income in
          the model without asthma severity was nearly unchanged
        
      
      
        Discussion
        Asthma-related morbidity and mortality have risen
        Hospitalization for asthma, a potentially avoidable
        outcome, is an important population-level marker of asthma
        severity. In this prospective study of adults with
        continued access to medical care for asthma, we identified
        two demographic factors (low income and non-white race)
        that were associated with a greater risk of hospitalization
        for asthma. Reliance on the emergency department for urgent
        asthma care was also associated with a greater risk of
        subsequent hospitalization. Greater asthma severity, as
        indicated by recent asthma hospitalization and systemic
        corticosteroid use, was related to an increased likelihood
        of hospitalization.
        Ecologic studies, based on US census data, have
        demonstrated a strong inverse relationship between median
        household income and hospitalization rates for asthma [ 4,
        geographic regions have higher rates of asthma
        hospitalization, even after accounting for race and
        urbanicity [ 5]. Investigators have also observed a similar
        association between community income level and mortality
        from adult asthma [ 33, 34, 35]. Since these studies lack
        individual-level income data, investigators have urged
        cautious interpretation [ 6]. The present study, using
        individual level data, supports the association between
        lower household income and a greater risk of
        hospitalization. The relationship between lower income and
        hospitalization is less strong in the model including
        asthma severity and health status, suggesting that greater
        asthma severity may mediate this association.
        The relationship between low income and asthma
        hospitalization has many potential explanations, including
        inadequate health care access. Low income persons in a
        population-based survey were approximately three times more
        likely to report difficulty paying for physician bills or
        prescription drugs than those persons with higher income [
        36]. Among adults hospitalized for asthma at a single
        institution, nearly one-third of low income subjects
        indicated no usual source of outpatient asthma care at
        nearly all subjects reported health insurance and access to
        ambulatory care for asthma, making this an unlikely
        explanation. Moreover, excluding subjects without baseline
        health insurance coverage had no appreciable affect on the
        results.
        Beyond health care access, the process of asthma care
        may be less adequate among low income persons. Haas 
        et al found that, after admission to
        the hospital for asthma, low income patients received lower
        intensity asthma management than those patients with higher
        between a surrogate marker of low income (unemployment) and
        high daily beta agonist use [ 20], which is an established
        risk factor for asthma hospitalization [ 37]. In a managed
        care setting, which should ensure health care access, low
        income asthma patients were less likely to visit an asthma
        for other exacerbating factors, such as cockroach antigen
        exposure [ 6, 38], cigarette smoking, secondhand smoke
        exposure [ 39], or viral upper respiratory infections.
        African-American race has been associated with higher
        hospitalization rates for asthma in both population-based [
        Socioeconomic status and health care access, however, may
        confound the relationship between race and hospitalization.
        Several small-area analyses found higher asthma
        hospitalizations rates among African-Americans, after
        analyses have found no effect of race, after taking income
        through Medicaid, investigators still observed higher
        hospitalization rates for African-Americans with asthma [
        greater risk of hospitalization for asthma in managed care
        taking insurance status into account, a national survey
        found a higher proportion of African-Americans reporting
        difficulty affording medical care than that of whites [
        36]. Our study suggests that the increased risk of
        hospitalization for asthma among African-Americans is not
        entirely explained by income, education, or health care
        access, which were controlled by design or analysis.
        We also discovered a suggestion that persons of Hispanic
        race or ethnicity had a higher risk of hospitalization for
        asthma compared with white, non-Hispanic adults. Previous
        studies focusing on Hispanic persons have provided
        inconsistent findings. Studies from New York City and
        Boston indicate that Hispanic persons are hospitalized more
        frequently for asthma [ 4, 6], whereas previous data from
        California have not found an increased risk [ 5]. Other
        studies have demonstrated a decreased morbidity and
        The heterogeneity of persons of Hispanic race or ethnicity
        may explain these variable results.
        Higher severity-of-asthma scores were associated with a
        greater risk of hospitalization for asthma. On examining
        disease-specific severity in more detail, we found that
        recent asthma hospitalizations and systemic corticosteroid
        use accounted for most of this increased risk, whereas
        recent respiratory symptoms and other asthma medication use
        were not predictive. In a recent analysis of adult health
        maintenance organization members with asthma, systemic
        steroid use and previous hospitalization were also
        study of hospitalized asthma patients similarly found that
        both factors were related to rehospitalization [ 43].
        Neither study, however, controlled for sociodemographic
        characteristics, such as low income, that are associated
        with hospitalization risk. In the present study,
        disease-specific severity was associated with a greater
        risk of hospitalization, controlling for other demographic,
        clinical, and health care access factors.
        Our findings differ from previous studies that found
        female gender and current smoking as risk factors for
        asthma hospitalization [ 9, 39]. Female gender has not
        consistently been related to hospitalization for asthma [
        44]. The lack of association with smoking could be
        explained by the 'healthy smoker effect' [ 45]. According
        to this principle, persons who develop smoking-related
        respiratory symptoms quit smoking, resulting in current
        smokers who are less susceptible to acute effects of
        smoking.
        Previous studies evaluating the effect of GERD on asthma
        morbidity have provided mixed results [ 46, 47]. In the
        present study, use of gastric acid suppression therapy, a
        potential surrogate for GERD, was associated with a greater
        risk of asthma hospitalization only in multivariate
        analysis that did not control for asthma severity. This
        suggests that increased asthma severity may function as a
        causal intermediate between GERD (or related conditions)
        and the increased likelihood of hospitalization for asthma.
        Consistent with this finding, Levin 
        et al found that treatment of GERD
        with omeprazole improved asthma-specific quality of life [
        30].
        Because adults with asthma treated by specialists
        usually have more severe asthma than those treated by
        generalist physicians [ 25], our study results should be
        generalized to the overall population of asthmatic persons
        with caution. Although our sampling method attenuates
        confounding by access to medical care for asthma, the
        results may not fully apply to populations without health
        care access. Also reflecting the sampling from specialty
        practices, study subjects had a higher median household
        income and educational attainment than the general
        population. Even so, low income was a risk factor for
        asthma hospitalization, suggesting that our findings may be
        more broadly applicable.
        The present study has additional limitations, including
        the reliance on self-reported health care utilization.
        Socioeconomic differences in recall or reporting of
        hospitalization, for instance, could influence the risk
        model. Although we were able to simultaneously consider
        demographic, clinical, and severity-related covariates, the
        current study does not fully elucidate the causal
        intermediates between predictors (eg income or race) and
        the risk of hospitalization. Finally, our use of
        self-reported health insurance status and source of regular
        asthma care may not fully ascertain other, more subtle,
        barriers to effective asthma care. Previous work has
        demonstrated that health insurance status does not fully
        explain health care-related financial problems [ 36].
        Transportation difficulties, work-related demands, and
        regional differences in health care quality may also have
        impeded access to efficacious asthma care. Despite these
        limitations, we believe the present study results may be
        generalized to persons with moderate to severe asthma.
      
      
        Conclusion
        Although the morbidity and mortality from asthma are
        increasing in the USA and around the world, the minority of
        adults with asthma will experience hospitalization or death
        from asthma. Targeted interventions could potentially
        benefit high-risk individuals in a cost-effective manner.
        Our results suggest that simple demographic and clinical
        features, especially low income, non-white race, previous
        hospitalization history, systemic corticosteroid use, and
        reliance on emergency department for urgent asthma care,
        can identify such high-risk patients for more intensive
        therapy.
      
      
        Supplementary material
        
          Subject recruitment and retention
          In brief, we recruited a random sample of certified
          American Board of Medical Specialty pulmonary specialists
          and allergy/immunology specialists. The participating
          years with outpatient visits for asthma over a
          prospective 4-week period. Each person registered by a
          participating physician was contacted to arrange a
          telephone interview.
        
        
          Risk factor variables
          We ascertained household income as a series of
          $75,000). To convert to specific income levels, the
          mid-increment value was applied (except for the highest
          category, where we used a value of $87,500).
          The severity-of-asthma score systemic corticosteroid
          sub-scale includes items for any past corticosteroid use,
          The asthma medication subscale incorporates current use
          of inhaled corticosteroids, inhaled non-steroidal
          anti-inflammatory agents, inhaled bronchodilators, oral
          beta agonists and theophylline-containing medications,
          nasal medications (antihistamines, decongestants, and
          topical corticosteroids), and home nebulizer use. In this
          subscale, one point is assigned for each medication used
          during the past 2 weeks, with one additional point for
          frequent inhaled beta agonist or corticosteroid use.
          We measured generic health status using the Medical
          Outcomes Study SF-36 questionnaire. Previous work
          demonstrates the SF-36 instrument's validity in adult
          scores have been defined from the eight SF-36 subscales
          by factor analysis [ 32], which measure physical and
          mental dimensions of health, respectively. Each summary
          score in the general US population has a mean of 50 and a
          favorable health states.
        
      
    
  
```
This example shows the usage of `grep -v` to search for lines without the character `1`. This can be useful to search for lines without numbers in order to primitively avoid a few citations in a text at random, though it does overfilter by picking out other lines in addition.


2. Option 2:
Example 1:
```
(base) prajitrajkumar@tuyihkj31798euoij831 biomed % grep "medic." rr37.txt
        Asthma is a common condition in general medical
          other asthma medications (besides systemic
          care, a principal care provider for asthma, medical
          deduction for outpatient medical care. We also identified
          use, other asthma medication use, past intubations, and
          medical provider for asthma care at baseline interview.
          outpatient medical care, a substantial proportion (16%)
          medication, were also associated with a greater risk of
          other asthma medications (OR, 1.1; 95% CI, 0.8-1.6) or
        continued access to medical care for asthma, we identified
        difficulty affording medical care than that of whites [
        recent respiratory symptoms and other asthma medication use
        confounding by access to medical care for asthma, the
          The asthma medication subscale incorporates current use
          beta agonists and theophylline-containing medications,
          nasal medications (antihistamines, decongestants, and
          subscale, one point is assigned for each medication used
```
This example shows the usage of `grep` with regular expressions. In this case, all instances of words that start with `"medic"` are found, which can be useful to find keywords that may vary slightly.


Example 2:
```
(base) prajitrajkumar@tuyihkj31798euoij831 biomed % grep "mmm*" rr74.txt
        circulation in many mammals. NO has been proposed as a
        immunohistochemistry.
          radioimmunoprecipitation assay (RIPA) buffer (1×PBS, 1%
          RIPA 100 mmol/l sodium orthovanadate). Samples were
          Immunohistochemistry
          Immunohistochemistry
        immunolocalization to the periphery of the lung. This,
        peripheral immunolocalization is in accord with previous
        waste products, including ammonia, that may contribute to
        lung inflammation and induction of iNOS, as the combination
        of hypoxia and inflammation has previously been reported to
        hypoxia and inflammation [ 23]. Others have also reported
        our current finding, however, immunohistochemical
        In summary, we identified a unique pattern of NOS
        chain reaction; RIPA = radioimmunoprecipitation assay; RVsP
```
Another example of `grep` with regular expressions. In this case, all instances of words with pattern `"mm"` are found, which can once again be useful to find certain keywords.

3. Option 3:
Example 1:
```
(base) prajitrajkumar@tuyihkj31798euoij831 biomed % grep [^a-z] rr37.txt
zsh: no matches found: [^a-z]
```
This command uses `grep` with metacharacters in order to search for lines that do not contain characters `a` through `z`, which may be useful for looking for numerical lines.

Example 2:
```
(base) tuyihkj31798euoij831:biomed prajitrajkumar$ grep [y-z] rr37.txt
        practice, accounting for about 1% of all ambulatory visits
        in the USA [ 1]. The mortality rate from asthma has risen
        sharply since the late 1970s, which may reflect increasing
        disease severity [ 2]. The hospitalization rate, another
        population-level marker of asthma severity, remains
        substantial [ 2], generating nearly one-half of all US
        health care costs for asthma [ 3]. Hospitalization rates
        for asthma have actually increased in some demographic
        subgroups, such as young adults [ 2] and the urban poor [
        factors underlying hospitalization for asthma could help
        elucidate the recent rise in asthma morbidity.
        contribute to increased hospitalization risk among adults
        with asthma. Demographic characteristics, such as poverty,
        risk of hospitalization for asthma [ 2, 4, 5, 6, 7, 8, 9,
        asthma care have also been frequently cited as contributing
        characteristics, health care access, and disease severity
        hospitalization risk is potentially confounded by
        inadequate health care access. Because many studies rely on
        ecologic socioeconomic and hospitalization data,
        individual-level factors - especially asthma severity -
        cannot be adequately examined [ 4, 5, 6, 7, 8, 15, 16, 17,
        18]. Other studies have not yet provided prospective
        follow-up [ 9, 10, 19, 20] or have not simultaneously
        In this article, using a prospective cohort study of
        demographic characteristics and asthma severity on
        subsequent hospitalization for asthma. Since study subjects
        were recruited from a random sample of physician practices,
        they all had access to health care for asthma. As a result,
        asthma severity on hospitalization, independent of health
          longitudinal cohort study of adults with asthma recruited
          from physician practices in Northern California. Details
          of the study design have been previously reported [ 23,
          demographic characteristics, smoking history, asthma
          history, symptoms, and treatment, health status, health
          care utilization for asthma, and insurance for asthma
          Physicians registered 669 eligible patients. After
          registry) and 242 of the follow-up subjects (65% of
          to eliminate all interviews potentially compromised by
          faulty data collection or documentation by a single
          survey interviewer [ 26, 27]. This restricted data set
          outside the study age range and 206 baseline subjects
          the 371 baseline subjects, the present study excludes an
          study findings.
          n = 129) were younger (36.6 years
          versus 40.5 years) and less likely to have white
          race/ethnicity (62% versus 71%; 
          P = 0.10, respectively). There were
          no statistical differences in history of ever smoking
          66%), atopic history (82% versus 83%), or
          severity-of-asthma scores (11.0 versus 10.6; 
          Hospitalization for asthma
          The primary study outcome was self-reported
          hospitalization for asthma during the 18-month
          18-month follow-up interviews whether they had been
          hospitalized for asthma during the previous 18 months.
          response, we analyzed the binary outcome of one or more
          hospitalization for asthma.
          smoking history was assessed using questions adapted from
          the National Health Interview Survey [ 28].
          We previously developed and validated a 13-item
          disease-specific severity-of-asthma score with four
          subscales: frequency of current asthma symptoms (daytime
          or nocturnal), use of systemic corticosteroids, use of
          other asthma medications (besides systemic
          corticosteroids), and history of hospitalizations and
          remote hospitalization on further hospitalization for
          hospitalization from the established severity score and
          defined two new variables: recent hospitalization (during
          hospitalization (past hospitalization not meeting the
          hospitalization and intubation subscale now reflects only
          prior history of intubation.
          age of first asthma symptoms. Atopic history was defined
          by a reported history of allergic rhinitis or atopic
          dermatitis. Because prior work suggests an unexpectedly
          near fatal asthma [ 29], we ascertained any history of
          aspirin sensitivity at baseline interview. Since
          gastroesophageal reflux disease (GERD) may exacerbate
          asthma symptoms [ 30], we evaluated whether subjects were
          Outcomes Study SF-36 questionnaire [ 31, 32]. We assessed
          subjects who appeared to rely on emergency department
          Statistical analysis
          In a previous analysis of pulmonary and allergy
          specialist care, the severity-of-asthma score was
          associated with an increased risk of hospitalization at
          18-month follow-up [ 25]. The current study evaluates
          other risk factors for asthma-related hospitalization,
          taking baseline asthma severity into account. Because
          asthma severity may act on the causal pathway between a
          risk factor and subsequent hospitalization for asthma, we
          baseline asthma severity and generic health status. For
          hospitalization either directly, through poor
          self-management strategies, or indirectly, if poorly
          educated persons have greater asthma severity for other
          severity - respiratory symptoms, systemic corticosteroid
          previous hospitalizations - that are most strongly
          predictive of subsequent hospitalization.
          Interview data were analyzed using SAS 6.12 software
          (SAS Institute, Cary, NC, USA). We evaluated the
          of hospitalization for asthma during the ensuing 18-month
          baseline and follow-up interviews for all analyses.
          regression analysis, with separate models for each
          analysis to elucidate the independent association between
          hospitalization. In constructing the multivariate model,
          with hospitalization were entered into the final model.
          Reflecting the sampling method employed, all subjects
          identified a regular source of asthma care and a primary
          The majority of participants (97%) also reported having
          Approximately one-third of subjects indicated having
          annual insurance deductible for physician visits (31%).
          The majority of subjects continued to report health
          insurance coverage (96%) and ongoing primary asthma care
          appeared to rely on the ED for urgent asthma care.
          hospitalization: bivariate analysis
          Table 1shows that the mean baseline age was 40.5 years
          and the majority of subjects were female (73%). A
          majority of subjects indicated white, non-Hispanic
          race/ethnicity (71%).
          Thirty-nine subjects (16%) reported at least one
          hospitalization for asthma during the prospective
          associated with a greater risk of hospitalization for
          smokers had an increased likelihood of hospitalization,
          to a lower risk of hospitalization (OR, 0.8 per year of
          Clinical risk factors for hospitalization:
          bivariate analysis
          A greater severity-of-asthma score, excluding its
          hospitalization component, was associated with a higher
          risk of subsequent hospitalization for asthma (OR, 4.7
          Although remote asthma hospitalization did not appear
          related to risk of ensuing hospitalization, more recent
          hospitalization was strongly associated with increased
          variables that may reflect exacerbating factors, such as
          aspirin allergy and use of gastric acid suppression
          asthma hospitalization.
          Better baseline generic physical health status (SF-36)
          was associated with a slightly decreased risk of
          subsequent hospitalization (6% reduction in odds per 1
          reduction in the risk of hospitalization per 1 point (95%
          CI, 0-7%). Reliance on emergency department care was
          finally related to a greater risk of hospitalization (OR,
          Risk of hospitalization - multivariate
          analysis
          covariates on the prospective risk of hospitalization for
          asthma using multiple logistic regression analysis (Table
          hospitalization (OR, 3.1; 95% CI, 1.1-8.8) after
          controlling for asthma severity and the other covariates
          greater risk of hospitalization (OR 1.1 per $10,000
          exclude no relation to hospitalization (0.9-1.3).
          severity-of-asthma score (OR, 3.4 per 5-point increment;
          95% CI, 1.7-6.8) and recent hospitalization for asthma
          (OR, 8.3; 95% CI, 2.1-33.4) were strongly associated with
          an increased risk of hospitalization. Reliance on ED for
          hospitalization in more detail. African-American race was
          associated with an increased risk of hospitalization for
          Hispanic race/ethnicity also appeared related to
          hospitalization (OR, 4.0; 95% CI, 0.9-18.0). There was no
          severity and hospitalization, we repeated the
          multivariate analysis dividing the overall
          severity-of-asthma score into its four subscales. The
          systemic corticosteroid score (OR, 1.7 per 5-point score
          increment; 95% CI, 1.3-2.3) and recent hospitalization
          for asthma (OR, 9.7; 95% CI, 2.2-43.0) were significantly
          hospitalization, after controlling for covariates. There
          was, conversely, no statistical relationship between
          asthma symptom scores (OR, 1.2; 95% CI, 0.7-1.9) and the
          ensuing risk of hospitalization. Systemic corticosteroid
          use and recent asthma hospitalization, then, appear to
          drive the relationship between asthma severity and
          hospitalization for asthma.
          Because asthma severity could act as a causal
          hospitalization, we repeated the multivariate analysis
          excluding asthma severity and generic health status from
          the model (Table 3). In this analysis, low income was
          more strongly related to a greater risk of
          hospitalization for asthma (OR, 1.2; 95% CI, 1.02-1.4).
          Use of gastric acid suppression therapy was also
          intervals changed slightly, there were no other notable
          severity.
          insurance coverage (3%) were affecting study results, we
          repeated the multivariate analysis excluding these
          subjects. Only one of the 39 subjects hospitalized at
          analyses. For example, the estimate for lower income in
          the model without asthma severity was nearly unchanged
        Asthma-related morbidity and mortality have risen
        sharply in the USA since the late 1970s [ 2].
        Hospitalization for asthma, a potentially avoidable
        severity. In this prospective study of adults with
        that were associated with a greater risk of hospitalization
        for asthma. Reliance on the emergency department for urgent
        subsequent hospitalization. Greater asthma severity, as
        indicated by recent asthma hospitalization and systemic
        of hospitalization.
        household income and hospitalization rates for asthma [ 4,
        hospitalization, even after accounting for race and
        urbanicity [ 5]. Investigators have also observed a similar
        association between community income level and mortality
        cautious interpretation [ 6]. The present study, using
        hospitalization. The relationship between lower income and
        hospitalization is less strong in the model including
        asthma severity and health status, suggesting that greater
        asthma severity may mediate this association.
        hospitalization has many potential explanations, including
        population-based survey were approximately three times more
        likely to report difficulty paying for physician bills or
        36]. Among adults hospitalized for asthma at a single
        institution, nearly one-third of low income subjects
        3-month follow-up [ 14]. In the present study, however,
        nearly all subjects reported health insurance and access to
        ambulatory care for asthma, making this an unlikely
        Beyond health care access, the process of asthma care
        may be less adequate among low income persons. Haas 
        intensity asthma management than those patients with higher
        income [ 14]. Another study demonstrated an association
        between a surrogate marker of low income (unemployment) and
        high daily beta agonist use [ 20], which is an established
        risk factor for asthma hospitalization [ 37]. In a managed
        income asthma patients were less likely to visit an asthma
        specialist [ 10]. Low income may alternatively be a marker
        exposure [ 39], or viral upper respiratory infections.
        hospitalization rates for asthma in both population-based [
        Socioeconomic status and health care access, however, may
        confound the relationship between race and hospitalization.
        Several small-area analyses found higher asthma
        hospitalizations rates among African-Americans, after
        statistically controlling for income [ 4, 5, 15]. Other
        analyses have found no effect of race, after taking income
        hospitalization rates for African-Americans with asthma [
        13]. African-American asthma patients similarly had a
        greater risk of hospitalization for asthma in managed care
        settings with access to primary care [ 10, 20]. Even after
        taking insurance status into account, a national survey
        difficulty affording medical care than that of whites [
        36]. Our study suggests that the increased risk of
        hospitalization for asthma among African-Americans is not
        entirely explained by income, education, or health care
        access, which were controlled by design or analysis.
        race or ethnicity had a higher risk of hospitalization for
        inconsistent findings. Studies from New York City and
        Boston indicate that Hispanic persons are hospitalized more
        frequently for asthma [ 4, 6], whereas previous data from
        studies have demonstrated a decreased morbidity and
        mortality from asthma among Hispanic adults [ 40, 41, 42].
        The heterogeneity of persons of Hispanic race or ethnicity
        may explain these variable results.
        Higher severity-of-asthma scores were associated with a
        greater risk of hospitalization for asthma. On examining
        disease-specific severity in more detail, we found that
        recent asthma hospitalizations and systemic corticosteroid
        recent respiratory symptoms and other asthma medication use
        were not predictive. In a recent analysis of adult health
        maintenance organization members with asthma, systemic
        steroid use and previous hospitalization were also
        associated with greater risk of hospitalization [ 21]. A
        study of hospitalized asthma patients similarly found that
        both factors were related to rehospitalization [ 43].
        Neither study, however, controlled for sociodemographic
        with hospitalization risk. In the present study,
        disease-specific severity was associated with a greater
        risk of hospitalization, controlling for other demographic,
        asthma hospitalization [ 9, 39]. Female gender has not
        consistently been related to hospitalization for asthma [
        explained by the 'healthy smoker effect' [ 45]. According
        respiratory symptoms quit smoking, resulting in current
        morbidity have provided mixed results [ 46, 47]. In the
        present study, use of gastric acid suppression therapy, a
        risk of asthma hospitalization only in multivariate
        analysis that did not control for asthma severity. This
        suggests that increased asthma severity may function as a
        and the increased likelihood of hospitalization for asthma.
        with omeprazole improved asthma-specific quality of life [
        Because adults with asthma treated by specialists
        usually have more severe asthma than those treated by
        generalist physicians [ 25], our study results should be
        generalized to the overall population of asthmatic persons
        confounding by access to medical care for asthma, the
        results may not fully apply to populations without health
        care access. Also reflecting the sampling from specialty
        practices, study subjects had a higher median household
        asthma hospitalization, suggesting that our findings may be
        more broadly applicable.
        The present study has additional limitations, including
        the reliance on self-reported health care utilization.
        hospitalization, for instance, could influence the risk
        model. Although we were able to simultaneously consider
        demographic, clinical, and severity-related covariates, the
        current study does not fully elucidate the causal
        the risk of hospitalization. Finally, our use of
        asthma care may not fully ascertain other, more subtle,
        demonstrated that health insurance status does not fully
        regional differences in health care quality may also have
        limitations, we believe the present study results may be
        generalized to persons with moderate to severe asthma.
        Although the morbidity and mortality from asthma are
        increasing in the USA and around the world, the minority of
        adults with asthma will experience hospitalization or death
        from asthma. Targeted interventions could potentially
        features, especially low income, non-white race, previous
        hospitalization history, systemic corticosteroid use, and
        reliance on emergency department for urgent asthma care,
        can identify such high-risk patients for more intensive
        therapy.
        Supplementary material
          American Board of Medical Specialty pulmonary specialists
          and allergy/immunology specialists. The participating
          physicians maintained a registry of persons aged 18-50
          years with outpatient visits for asthma over a
          prospective 4-week period. Each person registered by a
          participating physician was contacted to arrange a
          category, where we used a value of $87,500).
          The severity-of-asthma score systemic corticosteroid
          sub-scale includes items for any past corticosteroid use,
          use during the past 12 months, and steroid dependency.
          anti-inflammatory agents, inhaled bronchodilators, oral
          beta agonists and theophylline-containing medications,
          topical corticosteroids), and home nebulizer use. In this
          Outcomes Study SF-36 questionnaire. Previous work
          demonstrates the SF-36 instrument's validity in adult
          asthma [ 31]. The physical and mental component summary
          by factor analysis [ 32], which measure physical and
          mental dimensions of health, respectively. Each summary
```
This command uses `grep` with metacharacters in order to search for lines that do contain characters `y` through `z`, which may be useful for looking for lines in a mass amount with certain characters

4. Option 4:
Example 1:
```
(base) tuyihkj31798euoij831:biomed prajitrajkumar$ grep -L "gene" *
1468-6708-3-1.txt
1471-2172-2-9.txt
1471-2202-4-12.txt
1471-2202-4-17.txt
1471-2210-2-6.txt
1471-230X-1-6.txt
1471-2334-1-21.txt
1471-2334-2-27.txt
1471-2377-2-6.txt
1471-2407-1-13.txt
1471-2407-2-22.txt
1471-2407-2-3.txt
1471-2431-2-11.txt
1471-2431-3-5.txt
1471-2458-1-9.txt
1471-2466-1-1.txt
1471-2490-3-2.txt
1471-5945-2-13.txt
1472-6955-2-1.txt
1472-6963-3-1.txt
1476-5918-1-2.txt
ar149.txt
bcr618.txt
cc1476.txt
cc1477.txt
cc1843.txt
cc1852.txt
cc2167.txt
cc2358.txt
cc367.txt
cc991.txt
cvm-2-4-187.txt
```
This command uses `grep` with `-L` and `*` to search through files for files not containing the word `"gene"`, which is useful for filtering out certain files not containing text on genetic information.

Example 2:
```
(base) tuyihkj31798euoij831:biomed prajitrajkumar$ grep -L "the" *
(base) tuyihkj31798euoij831:911report prajitrajkumar$ 
```
This is another instance of a command using `grep` with `L` and `*` to search through groups of files not containing certain words. In this case, it can again be used for filtering and shows that no files exist that do not contain the word `"the"`.
