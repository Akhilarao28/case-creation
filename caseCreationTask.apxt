trigger caseCreationTask on Case (after insert) {
    if(Trigger.isAfter && Trigger.isInsert)
    {
        List <Task> newtask= new List <Task>();
        for(Case caselst:Trigger.New)
        {
           if(caselst.Type=='How-to')
           {
              Task tsklst=new Task();
               tsklst.Subject='Share Knowledge Article';
               tsklst.Priority='High';
               tsklst.Status='In Progress';
               tsklst.OwnerId=caselst.OwnerId;
               tsklst.WhatId=caselst.Id;
               tsklst.ActivityDate=System.today().addDays(2);   
                newtask.add(tsklst);
           }
        }
        if(!newtask.isEmpty())
        {
            insert(newtask);
        }
        
    }
}