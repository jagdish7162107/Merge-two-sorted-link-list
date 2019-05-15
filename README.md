# Merge-two-sorted-link-list
Given two sorted link list which is sorted in increasing order. Merge the two together in one list which is in increasing order. 

Node* SortedMerge(Node* head1,   Node* head2)
{
    Node* res=NULL; Node *curr=NULL;
    if(head1==NULL)
    return head2;
    if(head2==NULL)
    return head1;
    while(head1!=NULL && head2!=NULL)
    {
        if(head1->data<=head2->data)
        {
            if(curr==NULL)
            {
                res=head1;
                curr=head1;
              
            }
            else {
                curr->next=head1;
                curr=head1;
                 }
                head1=head1->next;
            }
        else {
            if(curr==NULL)
            {
                res=head2;
                curr=head2;
            }
            else {
                curr->next=head2;
                curr=head2;
                 }
                head2=head2->next;
        }          
    }
    if(head1==NULL)
    curr->next=head2;
    else if(head2==NULL)
    curr->next=head1;
    
    return res;
}
